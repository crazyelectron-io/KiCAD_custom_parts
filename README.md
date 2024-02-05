# Customized components for KiCAD 7.0

This repository contains all components that I created or customized for use in my projects.
These components are the actual products bought and used, having the correct footprint.
I also like to customize most symbols a bit to make the pin layout more schematic-friendly as I try to draw the actual wires (if it does not get mixed with multiple other wires) in the circuit diagrams - Elektuur/Elektor style...

## Directory Outline

- [`~/3d/`](3d) is for KiCAD 3D files of the components.
- [`~/datasheets/`] contains the collected datasheets of the components in these libraries in PDF-format.
- [`~/footprints/`](footprints) is for holding the KiCAD footprint libraries (having extension `.kicad_mod`).
- [`~/symbols/`](symbols) is for the KiCAD schematic symbol libraries (having the extensio `.kicad_sym`).

## Custom libraries usage

KiCAD comes with an extensive set of libraries (Global libraries available for all projects) and these libraries are an addition/replacement with all the parts that are actually verified and used.
The libraries in this repository should be added to the project by cloning it as a Git submodule.
This makes the libraries available locally and they can be updated as needed.
After getting the libraries included in the workspace, the ones needed must be added to the library list in the KiCAD project.

To add this repository as submodule in a project, use the command `git submodule add https://github.com/crazyelectron-io/KiCAD_custom_parts.git` once in the root of the project.
When later committing the project repository, the submodule dependency is also registered and when cloning it again, run the following commands to get the submodule(s) back:

```bash
git submodule init
git submodule update
```

To use the updated libraries after a custom part is added or updated, just run `git submodule update` to retrieve the changed libraries.

## Maintaining the custom parts library

The workflow to add or update components in this repository is:

1. Clone the repository with `git clone https://github.com/crazyelectron-io/KiCAD_custom_parts.git` in a separate directory and open that directory in VS Code.
2. Add/change the required parts in the libraries (see below for details).
3. Commit the changes to the repository and push to GitHub.

### Add a schematic symbol based on an existing symbol in another library

In many cases I modify the symbols to make the pin ordering more function grouped.
I also like to know for sure which symbol I use so I can even reproduce it years later.
To use an existing symbol in another library as starting point for creating a new symbol, follow these steps:

1. Start the `Symbol Editor` and locate the symbol to be used as starting point and copy it (context menu).
2. Create a new library in the directory `~/symbols/` of this repository and give it the (shortened) name of the component - I use one library file per component for ICs.
3. Select the new library in the Symbol Editor and _Paste_ the symbol in the library.
4. From there it can be edited and saved once it is finished.
5. To use the upated library in projects, commit the change to the repository.
6. Run `git submodule update` in the project that needs the symbol and add the library as project library.

### Add a new schematic symbol

The workflow for adding a new symbol is similar, except that we don't copy a symbol from another librarye but start with a blank canvas.

### Add a footprint based on an existing footprint in another library

Just like with schematic symbols, I like to validate footprints to ensure they match with the components I buy.
The workflow is similar to schematic symbols:

1. Start the `FootprintEditor` and locate the footprint to be used as starting point and copy it (context menu).
2. Create a new library in the directory `~/footprints/` of this repository and give it the (shortened) name of the component - I use one library file per component for ICs for easy maintenance.
3. Select the new library in the Footprint Editor and _Paste_ the footprint in the library.
4. From there it can be edited and saved once it is finished.
5. To use the upated library in projects, commit the change to the repository.
6. Run `git submodule update` in the project that needs the footprint and add the library as project library.

### Add a 3D symbol

[ # TODO: ]
