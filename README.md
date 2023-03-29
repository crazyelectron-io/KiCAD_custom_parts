# RP2040 with Ethernet and PoE

Hardware and firmware for creating an RP2040 based device that is powered through PoE and communicates over Ethernet (TCP/IP).

## Directory Outline

- [`~/hardware/`](hardware) is for KiCAD design files. When starting a new KiCAD project in this directory be sure to uncheck *Create a new direcotry for the project* in the **Create New Project** window.
- [`~/firmware/`](firmware) is for firmware souce code and binaries.
- [`~/mechanical/`](mechanical) is for mechanical CAD design files for the encloser or box. Create seperate directories for `.stl` or other files for 3D printing for easy accesss.

## KiCAD Libraries

Besides the default libraries provided with KiCAD 7.0, we also include the libraries provided by DigiKey (as a submodule), as well as our own libraries wuith tailored symbols and footprints.
To use these libraries after cloning the repository, run the following commands:

```bash
git submodule init
git submodule update
```

> To add another repository as submodule, use the command `git submodule add <URL_OF_REPOSITORY>`.
