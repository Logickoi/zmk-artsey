# ZMK ARTSEY Implementation

This repo contains the [ZMK](https://zmkfirmware.dev/) ARTSEY implementation and pre-built firmware for boards that have been setup to use ARTSEY by the core ARTSEY development team.

## Prebuilt Firmware

The `Releases` area of this repository contains the latest builds of the ZMK ARTSEY implementation. You can click on the most recent release and download the appropriate artifact for your MCU + board combination. Inside the zip file will be the necessary file for flashing your MCU.

### Firmware Files

Inside the firmware zip file will be 4 files

- `artsey.dtsi`: The ARTSEY definition that was used for the build
- A file with `.dts.pre.tmp` at the end that is the generated DTS file used for the build (this is for any required troubleshooting)
- A file with `-zmk-artsey.hex` at the end that is the hex firmware image that can be used to flash your MCU
- A file with `-zmk-artsey.uf2` at the end that is the uf2 firmware image that can be used to flash your MCU

Please Note: the `hex` and `uf2` files may or may not be present depending on your MCU + board combo. **PLEASE** use the proper file for flashing your board. 

**We are NOT responsible for any failed firmware flashes!**

## Adding ARTSEY Support

If you'd like to add ARTSEY support to a board that supports ZMK but is not built by this repo. Please follow the standard ZMK docs on how to add a new shield but using this repo as your `zmk-config` and open a Pull Request.

Also, update the `.github/workflows/build.yml` file for the new board being submitted.

Note: This repo is setup with github actions so you *can* work directly via GitHub Actions similar to how the ZMK documentation outlines.

## Licensing

Unless otherwise stated all source code is licensed under the [Apache 2 License](LICENSE-APACHE-2.0.txt).

Unless otherwise stated the non source code contents of this repository are licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](LICENSE-CC-Attribution-NonCommercial-ShareAlike-4.0-International.txt)

## Specific addenda [testing how deleted content is versioned] from Logickoi

Still learning this. Serious caveat emptor to anyone who uses anything I write! ;-)

With grateful appreciation to everyone upstream whose work made this possible. 

## Layout customizations - planned and/or actual

My planned changes from the baseline ARTSEY.IO layout, https://raw.githubusercontent.com/artseyio/artsey/main/layout%20diagrams/current.jpg

Testing - currently in the code, or may be otherwise mucking with:

-Swap the "." and "," keys. I find their reverse config easier to use.

Future - still to come:

-Update the lag time to be lower, to (eventually) allow for faster typing.

-Change "lower-left-hold" custom layer from volume/etc. controls to instead be nav controls. New key identities, by position:
--A: end
--R: up 
--T: home  
--S: (maybe escape??)
--E: right
--Y: down 
--I: left 
--O: ...is the key held down to activate layer.

-Change "upper-right-hold" layer from parentheses in their current layout, to instead be (by position):
--A: ...is the key held down to activate layer.
--R: colon
--T: close parentheses
--S: open parentheses
--E: ...is directly under the held key and so is hard to access, likely leave blank.
--Y: semicolon
--I: close brackets
--O: open brackets

-Change current "lower right hold" layer (symbols) from their current layout, to instead be (by position):
--A: ...is directly above the held key and so is hard to access, likely leave blank.
--R: question mark
--T: at-sign
--S: asterisk
--E: ...is the key held down to activate the layer 
--Y: dash
--I: percent sign   
--O: "generic" (non-oriented) double quote mark

If I get fancy later, may also consider repurposing the original direction/lock and bluetooth/lock key layer configs

Also someday may look at options for programming both right & left on same boad with a switch keycode. (Stretch goals!)

-...copying in that list template for later use:
--A:
--R:
--T:
--S:
--E:
--Y:
--I: 
--O: