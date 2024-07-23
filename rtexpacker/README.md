# `rTexPacker`

A simple and easy-to-use textures packer and font atlas generator.

## What can I do with `rTexPacker`?

`rTexPacker` is a powerful tool to package sprites or fonts into an atlas, to improve drawing performance on games.
Multiple images can be automatically organized (packed) into a single bigger image, as well as the multiple text characters of a font required by a game.
Packaging method can be configured with several option like packaging algorithm, padding and spacing between image.

Sprite origin can be defined and exported on the atlas descriptor file. Sprite shaders can be applied for special visual effects.

With `rTexPacker` you can easely package sprites and export atlas information in multiple formats (XML, JSON, CODE...).

## Features

 - Package **sprites and font glyphs** into an atlas
 - Configure **packing algorithms and heuristics**
 - Setup sprites **spacing, padding and alpha-trimming**
 - **Font generation options:** Size, SDF fonts, fixed font height
 - Import **custom unicode charset** from UTF-8 file
 - **Unicode** charset duplicates removed automatically
 - **Edit sprites origin** visually, exported with the atlas
 - Apply **per-sprite shaders** for special effects
 - Atlas **visualization options**: Zoom, Pan, Background, Fill
 - Multiple UI styles available, selectable from main toolbar
 - Load/Save **portable self-contained .rtp file**, containing all sprites
 - Load sprites from **multiple image formats**: `.png`, `.qoi`, `.tga`, `.jpg`
 - Load sprites from **font files**: `.ttf`, `.otf`
 - **Export atlas descriptor** as: text (`.rtpa`), binary (`.rtpb`), `.json`, `.xml` and code (`.h`)
 - **Export atlas image** as: `.png`, `.qoi`, `.dds` and `.raw`
 - Export atlas descriptor as **binary PNG chunk**: `rTPb`
 - Export **missing font codepoints** from requested list
 - **Multiple usage examples** provided to load: `.rtpa`, `.rtpb`, PNG chunk `rTPbp` and code `.h`.
 - Maximum atlas size up to **16384x16384 pixels**
 - Application **initialization configuration** automatically saved
 - Command-line support for **batch sprites packing**
 - **Completely portable (single-file, no-dependencies)**

## Basic Usage

Open the tool, drag & drop your sprites/fonts and setup atlas packing options.

Generated atlas can be exported as atlas-descriptor text file plus an atlas image file. The formats supported are:

 - Atlas Descriptor: text (`.rtpa`), binary (`.rtpb`), `.xml`, `.json` and code (`.h`)
 - Atlas Image: `.png`, `.qoi`, `.dds` and `.raw`

`rTexPacker` dektop version comes with command-line support for batch sprite packaging and font atlas generation.

 > rtexpacker.exe --help

## Keyboard/Mouse Shortcuts

 - `F1` - Show Help window
 - `F2` - Show About window
 - `F3` - Show Sponsor window

**File Options**
 - `LCTRL + N` - New atlas project (.rtp)
 - `LCTRL + O` - Load atlas project (.rtp)
 - `LCTRL + S` - Save current atlas project (.rtp)
 - `LCTRL + E` - Export current atlas project
 - `LCTRL + X` - Close current atlas project

**View Options**
 - `F5` - Toggle Sprites window
 - `F6` - Toggle Atlas Settings window
 - `R` - Toggle Sprites rectangles
 - `O` - Toggle Sprites origins

**Atlas Controls**
 - `MOUSE WHEEL` - Zoom in/out
 - `MOUSE MIDDLE BTN` - Image Panning
 - `F` - Zoom and center atlas to screen

**Sprite Controls**
 - `MOUSE LEFT BUTTON` - Select sprite(s) rectangle
 - `LCTRL + MOUSE LEFT BTN` - Select/unselect sprites
 - `G` - Toggle selected sprite origin edition mode
 - `D` - Zoom and center selected sprite to screen
 - `LSHIFT + LEFT` - Move selected sprite left on list
 - `LSHIFT + RIGHT` - Move selected sprite right on list
 - `DELETE` - Remove selected sprite
 
**Sprite Shader Controls**
 - `J` - Set shader for selected sprite(s)",
 - `LCTRL + J` - Toggle shader for selected sprite(s)",
 - `U` - Unload shader, return to default shader",

## Command-line

```
  USAGE:\n\n");
    > rtexpacker [--help] --input <directory>,[file01.ext],[file02.ext] [--output <filename.ext>]
                 [--atlas-desc <value>] [--atlas-image <value>]
                 [--atlas-format <value>] [--atlas-size <value>]
                 [--pack-algorithm <value>] [--pack-heuristic <value>]
                 [--padding <value>] [--trim-alpha] [--debug]
                 [--font-size <value>] [--font-charset <file.txt>]
                 [--font-force-height] [--font-force-width] [--font-sdf]

  OPTIONS:\n
    -h, --help                      : Show tool version and command line usage help
    -i, --input <directory>,[file01.ext],[file02.ext]...
                                    : Define input files. Comma separated:
                                        Directories to scan: <no extension>
                                        Multiple sprites: .rtp, .ttf, .otf
                                        Single sprites:   .png, .qoi, .bmp, .tga, .jpg, .jpeg
    -o, --output <filename.ext>     : Define output filename.
                                      Supported extensions: .rtpa, .rtpb, .xml, .json, .h
                                      NOTE: If not specified, defaults to: atlas.rtpa + atlas.png
    -ad, --atlas-desc <value>       : Define atlas descriptor output format:
                                        0 - TEXT (.rtpa)
                                        1 - BINARY (.rtpb)
                                        2 - XML (.xml)
                                        3 - JSON (.json)
                                        4 - CODE (.h)
    -ai, --atlas-image <value>      : Define atlas image output format:
                                        0 - PNG (.png)
                                        1 - QOI (.png)
                                        2 - DDS (.dds)
                                        3 - RAW (.raw)
    -af, --atlas-format <value>     : Define atlas image output pixel format:
                                        0 - GRAYSCALE
                                        1 - GRAY + ALPHA
                                        2 - R5G6B5
                                        3 - R8G8B8
                                        4 - R5G5B5A1
                                        5 - R4G4B4A4
                                        6 - R8G8B8A8 (default)
    -as, --atlas-size <value>       : Define atlas size: 128,256,512,1024,2048,4096,8192,16384\n
    -pa, --pack-algorithm <value>   : Define atlas packing algorithm
    -ph, --pack-heuristic <value>   : Define atlas packing heuristic
    -pd, --padding <value>          : Define sprites padding
    -sp, --spacing <value>          : Define sprites spacing in atlas
    -ta, --trim-alpha               : Define sprites alpha trimming
    -fs, --font-size <value>        : Define font size (height)
    -fc, --font-charset <file.txt>  : Use provided charset to generate atlas
    -fh, --font-force-height        : Force font height for all glyphs
    -fw, --font-force-width         : Force font monospace width
    -sdf, --font-sdf                : Generate SDF font
    -db, --debug-background         : Draw MAGENTA background into atlas image
    -dl, --debug-lines              : Draw sprite bound lines into atlas image
    -do, --debug-origins            : Draw sprite origin point into atlas image
    -pr, --png-rtpb                 : Export rTPb chunk in PNG atlas image

  EXAMPLES:\n
    > rtexpacker --input resources --output atlas.rtpa
        Process <resources> directory to generate <atlas.rtpa> + <atlas.png>
    > rtexpacker --input sprite01.png,sprite02.tga,sprite03.jpg --output atlas.json
        Process <sprite01.png>,<sprite02.tga>,<sprite03.jpg> to generate <atlas.json> + <atlas.png>
    > rtexpacker --input myatlas.rtp -ta -d
        Process <myatlas.rtp> to generate <atlas.rtpa> + <atlas.png> with sprites trimmed and debug rectangles
    > rtexpacker --input Arial.ttf --output atlas.xml -fs 32 -sdf
        Process <Arial.ttf> font to generate <atlas.xml> + <atlas.png>, font size 32 and SDF font
```

## Technologies

This tool has been created using the following open-source technologies:

 - [raylib](https://github.com/raysan5/raylib) - A simple and easy-to-use library to enjoy videogames programming
 - [raygui](https://github.com/raysan5/raygui) - A simple and easy-to-use immediate-mode-gui library
 - [rpng](https://github.com/raysan5/rpng) - A simple and easy-to-use library to library to manage png chunks
 - [rini](https://github.com/raysan5/rini) - A simple and easy-to-use config init files reader and writer
 - [tinyfiledialogs](https://sourceforge.net/projects/tinyfiledialogs/) - File dialogs for desktop platforms

## Handmade Software

`rTexPacker` is handmade software, it has been meticulously developed using the C programming language, with great attention put on each code line written.
This approach usually results in highly optimized and efficient code, but it is also more time-consuming and require a higher level of technical skills.
The result is great performance and small memory footprint.

`rTexPacker` is self-contained in a single-executable of about **1 MB**, it could fit on a floppy disk.

## Issues & Feedback

Note that the one-time-payment desktop version of `rTexPacker` comes with no support. Still, tool issues and feedback can be reported at https://github.com/raylibtech/rtools. They are reviewed with low-priority.

For additional support, priority issues review or tool customization requirements, please contact `ray[at]raylibtech.com`

## License

The use of `rTexPacker` desktop application is subject to the terms and conditions of the `End User License Agreement`.
By using `rTexPacker`, the user agrees to be bound by the terms of the EULA.

Check included `End User License Agreement` document for details (EULA.txt).

*Copyright (c) 2019-2024 raylib technologies ([@raylibtech](https://twitter.com/raylibtech)) | Ramon Santamaria ([@raysan5](https://twitter.com/raysan5))*
