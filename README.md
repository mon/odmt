# OpenSCAD DXF Merge (and clean) Tool (odmt)

OpenSCAD have two missing things when you export a DXF file : 
- no support for polylines
- no support for layers
  
No worries, the `odmt` tool tries to fill this gap. Written in Python with the help of the [ezdxf](https://bitbucket.org/mozman/ezdxf) library, `odmt` takes as argument one or more paths to DXF files and/or one or more paths to directories containing DXF files to merge together, each file is merged into a separate colored layer. On top of that, `odmt` converts all continuous segments (LINE) into a single polyline. More options explained below.

> This is my first python program, be cool and suggest improvements, thanks.

# Installation
Simply copy the `odmt` script (odmt.py) to your favorite location and install the [ezdxf](https://bitbucket.org/mozman/ezdxf) library.
```
pip install ezdxf
```
or more simple clone the repository (the ezpdf library is packed with)
```
git clone https://github.com/lautr3k/odmt.git
```

# Usage
```
usage: odmt [-h] [--input path [path ...]] [--output path]
            [--search pattern [pattern ...]] [--ignore pattern [pattern ...]]
            [--colors index [index ...]] [--nolayers] [--version]

OpenSCAD DXF Merge Tool (odmt) - v1.0.0

optional arguments:
  -h, --help            show this help message and exit
  --input path [path ...], -i path [path ...]
                        input file or directory - default: [./input]
  --output path, -o path
                        output file - default: ./output/merged.dxf
  --search pattern [pattern ...]
                        search file pattern - default: [*.dxf]
  --ignore pattern [pattern ...]
                        ignored file/directory pattern - default: [*_ignore_*]
  --colors index [index ...]
                        layers indexed colors - default: [10, 20, 30, 40, 50,
                        60, 70, 80, 90, 100, 110, 120, 130, 140, 150, 160,
                        170, 180, 190, 200, 210, 220, 230, 240]
  --nolayers            if set, all files will be merged into the same layer
  --version, -v         show program's version number and exit
  ```
  
  
