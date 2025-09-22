# `rImageShield`

A simple and easy-to-use image message embedder. 

## What can I do with `rImageShield`?

With `rImageShield` you can protect/sign your images embedding custom copyright/license messages. 

Message data distribution inside image can be customized, following an Uniform or Pseudo-Random distribution around the pixels; multiple other parameters can also be configured. Message can be compressed and encrypted with a password for maximum security.

Using `rImageShield` messages can be recovered, it automatically detects if one image contains a message on loading.

## Features

 - Multiple **input image file formats**: `.png`, `.qoi`, `.bmp`, `.tga`, `.raw`
 - Editable text input message, **up to 256 characters**
 - Message **compression and encryption** support
 - Uniform and PRNG data **distribution settings**
 - Detailed image, message and distribution information
 - Multiple message **visualization modes**: ASCII, Hexadecimal, Grayscale
 - Visual **shield watermark option** available
 - **Export image** as `.png`, `.qoi` or `.raw`
 - Multiple UI styles supported, select your best style
 - Command-line support for **image message recovering**
 - **Completely portable (single-file, no-dependencies)**
 
## Basic Usage

Steps to add a message to an image:

1. **Load an image** by drag&drop or press the `Open File` button on top toolbar
2. **Edit text message** on provided textbox, grid shows message bytes details
3. **Config message compression/encryption** options (for extra data protection)
4. **Config message data distribution** options on right panel, uniform or pseudo-random
5. **Export image** with embedded message (`.png`, `.qoi` or `.raw`)

## Keyboard/Mouse Shortcuts

 - `F1` - Show Help window
 - `F2` - Show About window
 - `F3` - Show Issue Report window
 
**File Options**
 - `LCTRL + O` - Load image file
 - `LCTRL + S` - Save/Export image file
 - `LCTRL + X` - Close image file
    
**Message Controls**
 - `LCTRL + R` - Reset message to default
 - `LCTRL + C` - Copy message to clipboard
 - `LCTRL + V` - Paste message from clipboard
    
**Image controls**
 - `MOUSE LEFT BTN` - Image Panning
 - `MOUSE WHEEL` - Zoom in/out
 - `UP-DOWN-LEFT-RIGHT` - Move Image
 - `F` - Zoom and center image
 - `LCTRL + MOUSE MBTN + UP` - Soft zoom in
 - `LCTRL + MOUSE MBTN + DOWN` - Soft zoom out
 - `LCTRL + LSHIFT + MOUSE WHEEL` - Snap zoom
 - `ESCAPE` - Close Window/Exit
 
## Command-line

**WARNING: rImageShield command-line interface only supports message loading.**

**Batch image message embedding functionality is provided as a separate license.**

```
    USAGE:
        > rimageshield [--help] --input <imagefile.ext> --password <password>

    OPTIONS:
        -h, --help                      : Show tool version and command line usage help
        -i, --input <imagefile.ext>     : Define input file for message loading
                                        : Supported image formats: .png, .qoi
        -p, --password <password>       : Define password for encryption (max 16 bytes)

    EXAMPLE:
        > rimageshield --input image.png --password "123456"
```

## Technologies

This tool has been created using the following open-source technologies:

 - [raylib](https://github.com/raysan5/raylib) - A simple and easy-to-use library to enjoy videogames programming
 - [raygui](https://github.com/raysan5/raygui) - A simple and easy-to-use immediate-mode-gui library
 - [rpng](https://github.com/raysan5/rpng) - A simple and easy-to-use library to library to manage png chunks
 - [rini](https://github.com/raysan5/rini) - A simple and easy-to-use config init files reader and writer
 - [tinyfiledialogs](https://sourceforge.net/projects/tinyfiledialogs/) - File dialogs for desktop platforms
 - [monocypher](https://github.com/LoupVaillant/Monocypher) - An easy to use, easy to deploy crypto library

## Handmade Software

`rImageShield` is handmade software, it has been meticulously developed using the C programming language, with great attention put on each line of code written.
This approach usually results in highly optimized and efficient code, but it is also more time-consuming and require a higher level of technical skills.
The result is great performance and small memory footprint.

`rImageShield` is self-contained in a single-executable of about **1 MB**, it could fit on a floppy disk.

## Issues & Feedback

Note that the one-time-payment desktop version of `rImageShield` comes with no support. Still, tool issues and feedback can be reported at https://github.com/raylibtech/rtools. They are reviewed with low-priority.

For additional support, priority issues review or tool customization requirements, please contact `ray[at]raylibtech.com`

## License

The use of `rImageShield` desktop application is subject to the terms and conditions of the `End User License Agreement`.
By using `rImageShield`, the user agrees to be bound by the terms of the EULA.

Check included `End User License Agreement` document for details (EULA.txt).

*Copyright (c) 2022-2024 raylib technologies ([@raylibtech](https://github.com/raylibtech))*
