# Micromake D1 delta 3D printer docs

There is little information on the
[Micromake Delta 3D printer](http://micromakemicromake.aliexpress.com/store/2128317).
This repo & [wiki](https://github.com/sternlabs/micromake-docs/wiki)
are an attempt to improve this situation.

## General Information

Other information can be found at:
- [Micromake YouTube channel](https://www.youtube.com/c/MICROMAKE)
- [Micromake Google Drive](https://drive.google.com/drive/folders/0B1DQUrzkDP-tNDU0NXhVcGhlc0k)

The printer exists in different linear motion models:
- roller carriage (Micromake "pulley")
- linear rails
- smooth rods ("optic axis", possibly retired)

## (New) Control Board and Firmware

The control board is based on RAMPS and runs
[Repetier](https://github.com/repetier/Repetier-Firmware/).
Find `Configuration.h` in the respective model directory.  The
configuration has been created with the
[Repetier Firmware Tool](https://www.repetier.com/firmware/v092/),
based on
[Bogdan Brudiu's config](https://gist.github.com/bogdanbrudiu/117df165d2b2b20900aecfd09c60ea1e).

The firmware I received had a bad P1/P2/P3 probe coordinate
configured, which made it brick itself upon `G32` bed leveling.
To copy the settings from `Configuration.h` to the EEPROM, use `M502`,
followed by `M500`.
