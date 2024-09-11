## rImageShield Frequently Asked Questions

Here it is a list of questions about `rImageShield`. Feel free to send any other question to: ray[at]raylibtech.com

 > How does `rImageShield` work?

This tool uses a technique called [steganography](https://en.wikipedia.org/wiki/Steganography) that consists of embedding a message within another media (usually called a carrier). In this case, our carrier is the image and the message is a text string defined by users.

 > What are the practical uses of `rImageShield`?

This tool is intended to embed copyright/license messages into images to allow identifying the copyright-holders of the image with no need for additional external files. It could also add other kind of licensing information for the image.

 > How is the message embedded into the image?

Message is defined by a number of bits (usually 8 bits per character); those bits are distributed along the image pixels, using the [LSB bits](https://en.wikipedia.org/wiki/Bit_numbering) that conform the pixels. One pixel can contain up to 4 bits, so, 1 text character could be contained in 2 random image pixels. Note that a 2048x2048@RGB image has 4194304 pixels and +16 millions of LSB bits that can be modified. For a message that consists of 160 characters, only 1280 bits (160x8 = 1280 bits) of the image pixels are slightly modified.

 > Are the image pixel colors modified?

Yes, but in practice only some pixel are slightly modified and it's imperceptible by the human eye.

 > How are the message bits distributed around the image?

`rImageShield` offers two possible distribution methods: `Uniform` and `Random`. Uniform distribution allows distributing the bits in an uniform way, with options to select an offset and a spacing. `Random` uses a pseudo-random numbers generator to distribute the bits in a more uniform way around the image. Seed for the random-numbers generator can be configured by users.

 > What image file formats are supported?

`rImageShield` supports input images as `.png`, `.qoi`, .`bmp`, `.tga`, and `.raw`. It can export the image with the embedded message as lossless file formats: `.png`, `.qoi` and `.raw`. Just note that `.qoi` export is only available for 32bit RGBA images.

 > What is the maximum message size?

`rImageShield` is limited to text messages of 255 characters (bytes) long. Larger messages could be supported but it must be negotiated on a per-client request.

 > Is it possible to lose/corrupt the embedded message?

Yes, if the exported image is edited with an image-editor software and pixel colors are changed (i.e. brightness, contrast, hue...) or image is cropped/resized. Also, if the image is re-saved as a lossy image file format (like `.jpg`) the pixel colors change and consequently the message data is corrupted.

 > Is it possible to recover the embedded message?

Yes, knowing the distribution method and configuration parameters the embedded message can be recovered. But note that distributed message could have been previously compressed and/or encrypted, in those cases retrieving the original message could also requires a password.

 > How can I retrieve the embedded message?

Just open the image containing the embedded message with `rImageShield`. The program automatically tries to detect if a message has been previously embedded in that image and tries to recover it, asking for a password if required. In any case, when a message is detected in an image, independently if the message could be recovered or not, the program is locked to avoid embedding a new message into that image.

 > Could an image with an embedded message not being detected when opening with `rImageShield`?

It could happen. In that case, the message was probably corrupted and consequently lost. That image will be treated as an empty image, ready to store a new message.

 > How can I improve message protection on `rImageShield`?

If desired, `rImageShield` offers additional options to protect the plain text message. It can be [compressed](https://en.wikipedia.org/wiki/Data_compression) (it _usually_ reduces the size of the message) and it can also be [encrypted](https://en.wikipedia.org/wiki/Encryption). For encryption, a password is required and the same password should be provided when trying to load the image with the embedded message.

 > What algorithm is used for compression?

By default, [`DEFLATE`](https://en.wikipedia.org/wiki/Deflate) algorithm is used.

 > What algorithm is used for encryption?

By default, [`XChaCha20`](https://en.wikipedia.org/wiki/Salsa20#ChaCha_variant), combined with [`Poly1305`](https://en.wikipedia.org/wiki/Poly1305) for [MAC](https://en.wikipedia.org/wiki/Message_authentication_code) generation.

 > Are those methods secure? Can my embedded message be retrieved by other people?

It's VERY secure. Data is distributed around the image so the distribution method is required to get back the required bits from the image pixels. Also, if message is encrypted, the original password must be provided to decrypt it.

 > Can I upload my image with the copyright message into social networks? Can I send image by mail?

Unfortunately some social networks and mail services could use a lossy compression to reduce image size, changing the pixel colors in the process; in those cases the message could be lost but some social networks and mail services offer options to avoid images recompression or modification.

 > What is the `Shield watermark` option I can find on image export?

The `Shield watermark` is a sequence of random-colors 2-pixel border added to the image to identify that image has been processed with `rImageShield` and it contains a copyright/license message embedded. The `Shield watermark` is optional and actually can be removed at image loading without loosing the underlying pixel color.

The `Shield watermark` is a deterrent visual mark for users trying to use that image in a not copyright-complaing ways.

 > Is it possible to remove `Shield watermark`?

Yes, the `Shield watermark` is optional and can be just disabled on image export.

Additional, the `Shield watermark` does not corrupt underlying pixels. When image is reloaded and message is successfully retrieved the `Shield watermark` is removed from the image.

 > How could I check if my image has been stolen?

Only the creator of the image has the original image, that should be kept save and unpublished, and the image with the copyright message embedded. If a published image (with embedded copyright) has been stolen and published by someone else it can be demonstrated using the embedded (and password-protected) copyright message that only the original author can show.

 > If someone steals my image and edits it with an image-editor to remove message, how can I demonstrate the image had my copyright?

Proof through the inverse: if it doesn't contain your copyright, it's an stolen image and not the original. You should always keep your original image (previous to message embedding) as a safe-guard. **Only image containing copyright message should be distributed**.

_Please, send me your questions to `ray[at]raylibtech.com` to be added to the FAQ!_
