Hidden message, text, image, audio or other files in image
=================

[Free Download Steganography tool for Windows](https://easiestsoft.com/win/a-free-steganography-tool/)
-----------

Example: hide message into an image
-------------

```nim
import steganography_tool, flippy
var image = loadImage("example/box.png")
encodeMessage(image, "Please hide me")
image.save("example/out-box.png")
```

How to extract/decode message from steganography image
--------

``` nim
var image = loadImage("example/out-box.png")
echo decodeMessage(image)
```

Steganography how to hide text in image
---------

```nim
let text = readFile("example/secret.txt")
var image = loadImage("example/box.png")
encodeMessage(image, text)
image.save("example/out-box.png")
```

Steganography Hiding an image inside another image
---------

```nim
let src = readFile("example/secret.png")
var image = loadImage("example/box.png")
let tag = "tseisae_$"
encodeMessage(image, src & tag)
image.save("example/out-box.png")
```

Steganography hidden image decoder
------------

```nim
var img = loadImage("example/out-box.png")
let tag = "tseisae_$"
let decoded = decodeMessage(image, tag)
writeFile("example/out-secret.png")
```

Steganography hide audio in image
---------

```nim
let src = readFile("example/secret.mp3")
var image = loadImage("example/box.png")
let tag = "tseisae_$"
encodeMessage(image, src & tag)
image.save("example/out-box.png")
```

Steganography hidden audio decoder
------------

```nim
var img = loadImage("example/out-box.png")
let tag = "tseisae_$"
let decoded = decodeMessage(image, tag)
writeFile("example/out-secret.mp3")
```
---

This Steganography generator is based on [steganography](https://github.com/treeform/steganography)