# `rTexViewer`

A simple and easy-to-use textures viewer, editor and image board.

## What can I do with `rTexViewer`?

`rTexViewer` is a powerful image viewer and editing tool that allows you to organize images into an image board, perfect to generate moodboards for reference and inspiration. It also includes multiple image editing tools to optimize pixel format, crop, resize, flip or apply custom GLSL shader effects, including an integrated shader code editor with hot-reloading.

With `rTexViewer`, you can easily view and manage your game textures or sprites, and also export them in multiple formats.

## Features

 - **Three view image modes**: `TABS`, `BOARD` or `FOLDER`
 - Load/Save images/full-board as `.rtv` project file (non-destructive, image data compressed)
 - Load **image file formats**: `.png`, `.qoi`, `.bmp`, `.tga`, `.jpg`, `.gif`, `.hdr`, `.ppm`, `.pgm`
 - Load **compressed texture** formats: `.dds`, `.pkm`, `.ktx`, `.pvr`, `.astc` (if supported by GPU)
 - **Load images from URL (copy&paste)**, saved automatically into a `downloads` directory (Windows only)
 - View image options: `Zoom`, `Pan`, `Alpha`, `Background` and `Scale filter`
 - View image information: `Name`, `Size`, `Format`, `Memory`, `Selected Pixel info`, `Color Palette`
 - Edit images: Change image **pixel-format with real-time preview**
 - Edit images: `Flip`, `Rotate`, `Resize`, `Resize Canvas`, `Crop`, `Alpha Clean` and more
 - Edit images: **Visual crop mode**, just draw a rectangle and crop
 - Edit images: Define image **Text Description**, saved on `.rtv`
 - Edit images: Assign **GLSL shaders effects** to images, saved on `.rtv`
 - **Image shader code editor** with auto-hot-reloading of shader changes
 - **Multiple sample GLSL shaders provided** for reference and new effects creation
 - **Export** single images as `.png`, `.qoi`, `.dds`, `.raw` or byte array `.h`
 - **Export** full image board as a single image `.png`, `.qoi` or `.dds`
 - **Export image palette** as `.png` or `.pal` (up to 256 colors)
 - Multiple UI styles supported, including latest `Amber` style!
 - Multiple window options: clean mode, borderless, top-most, mouse pass-through
 - Command-line support for **batch image processing** and formats conversion
 - **Completely portable (single-file, no-dependencies)**

## Basic Usage

Open the tool, drag & drop your images and view/edit them or place/organize them in the board mode.

Edited image can be exported as `.png`, `.qoi`, `.dds`, `.raw` and `.h` code file. Images collection can be saved as a `.rtv` project file.

`rTexViewer` desktop version comes with command-line support for batch image processing and format conversion. Up to 256 chainned transformations can be applied per image on the command-line. For usage help:

 > rtexviewer.exe --help

## Keyboard/Mouse Shortcuts

 - `F1` - Show Help window
 - `F2` - Show About window
 - `F3` - Show Issue Report window

**File Options**
 - `LCTRL + N` - New project
 - `LCTRL + O` - Load image/board
 - `LCTRL + S` - Save image/board
 - `LCTRL + E` - Export image/board
 - `LCTRL + X` - Close image

**View Modes**
 - `1,2,3` - Switch view mode: Tabs, Board, Folder
 - `F5` - Toggle image Info window (uncomp. only)
 - `F6` - Toggle image Edit window (uncomp. only)
 - `F7` - Toggle image Shade Editor

**-Tabs/Folder mode controls**
 - `MOUSE WHEEL` - Zoom in/out
 - `MOUSE LEFT/MIDDLE BTN` - Panning
 - `LCTRL + LSHIFT + MOUSE WHEEL` - Fast zoom
 - `F` - Zoom to screen size and center
 - `A + MOUSE WHEEL` - Opacity change
    
**-Board mode controls**
 - `MOUSE WHEEL` - Board zoom in/out
 - `MOUSE LEFT BTN` - Image selection/movement
 - `MOUSE MIDDLE BTN` - Board panning
 - `LCTRL + MOUSE WHEEL` - Image zoom
 - `LCTRL + LSHIFT + MOUSE WHEEL` - Image fast zoom
 - `LALT + MOUSE WHEEL` - Image draw order
 - `SPACE` - Toggle image Lock

**Image Edit Options**
 - `H` - Flip image Horizontal
 - `V` - Flip image Vertical
 - `R` - Rotate image 90 degrees CW
 - `LCTRL + R` - Show Resize window
 - `LCTRL + K` - Show Visual Crop mode
 - `MOUSE LEFT BTN` - Draw crop rectangle"
 - `T` - Edit image text info

**Shader Editor (on mouse hover)**
 - `LCTRL + X` - Cut selected text
 - `LCTRL + C` - Copy selected text
 - `LCTRL + V` - Paste selected text
 - `LCTRL + Z` - Undo latest text changes
 - `LCTRL + X` - Undo latest text changes
 - `U` - Reset image shader

**View Options**
 - `C` - Toggle Clean mode
 - `G` - Toggle Grid mode (zoom +500%)

**Window Options**
 - `7` - Toggle undecorated window
 - `8` - Toggle top-most window
 - `9` - Toggle mouse-passthrough window
 - `0` - Toggle transparent background
 - `LALT + A + MOUSE WHEEL` - Window opacity
 - `MOUSE MIDDLE BTN` - Pan window (undecorated)"

**Images navigation**
 - `TAB` - Cycle to next image
 - `RIGHT/PAGE UP` - Show next image
 - `LEFT/PAGE DOWN` - Show previous image
 - `ESCAPE` - Close Window/Exit

## Command-line

```
  USAGE:
    > rtexviewer [--help] --input <filename.ext>
       [--output <filename.ext>] [--format <pixelformat>]
       [--resize <new_width>,<new_height>,[algorythm]]
       [--resize-canvas <new_width>,<new_height>,[offsetx],[offsety]]
       [--crop <x>,<y>,<width>,<height>]
       [--flip-horizontal] [--flip-vertical]
       [--rotate-cw] [--rotate-ccw]
       [--alpha-clear] [--alpha-crop] [--alpha-premultiply]
       [--make-pot] [--dithering] [--gen-mipmaps]
       [--palette <filename.ext>]\n

  OPTIONS:
    -h, --help                      : Show tool version and command line usage help
    -i, --input <filename.ext>      : Define input file\n
    -iraw, --input-raw <filename.raw>,<width>,<height>,<format>,<header>
                                    : Define raw input file\n
    -o, --output <filename.ext>     : Define output file
                                    : Supported extensions: .png, .ktx, .raw, .h\n
    -f, --format <pixelformat>      : Convert image pixel format\n
    -r, --resize <new_width>,<new_height>,[algorythm]
                                    : Resize image\n
    -rc, --resize-canvas <new_width>,<new_height>,[offsetx],[offsety]
                                    : Resize canvas\n
    -k, --crop <x>,<y>,<width>,<height>]
                                    : Crop image to rectangle\n
    -fh, --flip-horizontal          : Flip horizontal
    -fv, --flip-vertical            : Flip vertical
    -rcw, --rotate-cw               : Rotate CW
    -rccw, --rotate-ccw             : Rotate CCW
    -pot, --make-pot                : Make Power of Two
    -ac, --alpha-clear              : Clear alpha pixels
    -at, --alpha-trim               : Trim alpha border
    -ap, --alpha-premultiply        : Premultiply alpha
    -d, --dithering                 : Apply image dithering
    -gm, --gen-mipmaps              : Generate mipmaps

  EXAMPLE:
    > rtexviewer --input image.png --output output.png --format R5G5B5A1
```

## Technologies

This tool has been created using the following open-source technologies:

 - [raylib](https://github.com/raysan5/raylib) - A simple and easy-to-use library to enjoy videogames programming
 - [raygui](https://github.com/raysan5/raygui) - A simple and easy-to-use immediate-mode-gui library
 - [rpng](https://github.com/raysan5/rpng) - A simple and easy-to-use library to library to manage png chunks
 - [rini](https://github.com/raysan5/rini) - A simple and easy-to-use config init files reader and writer
 - [tinyfiledialogs](https://sourceforge.net/projects/tinyfiledialogs/) - File dialogs for desktop platforms

## Handmade Software

`rTexViewer` is handmade software, it has been meticulously developed using the C programming language, with great attention put on each line of code written.
This approach usually results in highly optimized and efficient code, but it is also more time-consuming and require a higher level of technical skills.
The result is great performance and small memory footprint.

`rTexViewer` is self-contained in a single-executable of about **1 MB**, it could fit on a floppy disk.

## Issues & Feedback

Note that the one-time-payment desktop version of `rTexViewer` comes with no support. Still, tool issues and feedback can be reported at https://github.com/raylibtech/rtools. They are reviewed with low-priority.

For additional support, priority issues review or tool customization requirements, please contact `ray[at]raylibtech.com`

## License

The use of `rTexViewer` desktop application is subject to the terms and conditions of the `End User License Agreement`.
By using `rTexViewer`, the user agrees to be bound by the terms of the EULA.

Check included `End User License Agreement` document for details (EULA.txt).

*Copyright (c) 2015-2024 raylib technologies ([@raylibtech](https://twitter.com/raylibtech)) | Ramon Santamaria ([@raysan5](https://twitter.com/raysan5))*
