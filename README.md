# NOTE!!! #

This project has been replaced by PyRMenuGen, a more modern and robust RMENU generator written in Python.

See here https://github.com/megatron-uk/PyRMenuGen

----

# Old Readme Contents #

This BASH shell script is used to generate the on-disc menu for the SEGA Saturn 'Rhea' SD Card reader, as designed and sold by [Deunan](http://gdemu.wordpress.com).

It uses the RMENU Saturn application as written by ['Neuroacid' on Assemblergames](http://assemblergames.com/l/threads/official-rhea-discussion.57377/).

## Useage ##

Your SD card must be formatted (FAT32), your games (either bin/cue, CloneCD .CCD or Discjuggler .CDI) must be in the numerically named folders on the SD card starting from '02' upwards. One per folder as normal.

The installation of Neuroacid's RMENU code must be unzipped in the '01' folder.

The script runs, and by default makes no changes. See the help text (--h) for full details. It identifies all the Saturn image files present on the SD card and generates the MENU.LIST file that RMENU expects and then makes a new ISO image (using mkisofs) with the RMENU binaries and the MENU.LIST file.

On booting the Saturn, the RMENU application should show all of the images installed on the SD card, including title, disc number etc.

## Requirements ##

A mounted, formatted SD card with usual Rhea folder structure: 01, 02, 03 etc.

RMENU unzipped into the 01 folder.

The tools 'xxd' and 'mkisofs' on the host system.

Standard GNU tools including grep, awk, bash and sed. Cygwin should work fine.

## Limitations ##

Discjuggler .cdi files can be in slightly different formats; if Discjuggler was used to rip the disc originally, and the full suite of reccomended options was used (subcodes, pre-gaps, cdi-g etc.) then the full Saturn disc header information should always be present (title, version, disc number, region etc). However, for games ripped initially to bin/cue and then combined to a cdi via mounting in daemon tools, some of this information may not be present.

For best results, rip your original games using Discjuggler as it preserves the most information and is the most compatible with the Rhea device.

## Acknowledgements ##

The code is based on an initial version by [AlejandroVM from assemblergames](http://assemblergames.com/l/members/alejandrovm.101308/).
