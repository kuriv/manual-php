# GD

* [gd_info - 获取当前安装的 GD 库的信息]
* [getimagesize - 获取指定的图像大小]
* [getimagesizefromstring - 从指定的字符串中获取图像的大小信息]
* [image_type_to_extension - 获取指定的图像类型的文件后缀]
* [image_type_to_mime_type - 获取指定的图像类型的 MIME 类型]

## gd_info

```php
<?php

var_dump(gd_info()); // array(14) { ["GD Version"]=> string(26) "bundled (2.1.0 compatible)" ["FreeType Support"]=> bool(true) ["FreeType Linkage"]=> string(13) "with freetype" ["GIF Read Support"]=> bool(true) ["GIF Create Support"]=> bool(true) ["JPEG Support"]=> bool(true) ["PNG Support"]=> bool(true) ["WBMP Support"]=> bool(true) ["XPM Support"]=> bool(true) ["XBM Support"]=> bool(true) ["WebP Support"]=> bool(true) ["BMP Support"]=> bool(true) ["TGA Read Support"]=> bool(true) ["JIS-mapped Japanese Font Support"]=> bool(false) }

```

## getimagesize

```php
<?php

var_dump(getimagesize(__DIR__ . '/example.jpg'));
var_dump(getimagesize('https://github.com/fluidicon.png'));

```

## getimagesizefromstring

```php
<?php

var_dump(getimagesizefromstring(file_get_contents(__DIR__ . '/example.jpg')));
var_dump(getimagesizefromstring(file_get_contents('https://github.com/fluidicon.png')));

```

## image_type_to_extension

```php
<?php

var_dump(image_type_to_extension(IMAGETYPE_GIF));        // string(4) ".gif"
var_dump(image_type_to_extension(IMAGETYPE_JPEG));       // string(5) ".jpeg"
var_dump(image_type_to_extension(IMAGETYPE_PNG));        // string(4) ".png"
var_dump(image_type_to_extension(IMAGETYPE_PNG, false)); // string(3) "png"

```

## image_type_to_mime_type

```php
<?php

var_dump(image_type_to_mime_type(IMAGETYPE_GIF));  // string(9) "image/gif"
var_dump(image_type_to_mime_type(IMAGETYPE_JPEG)); // string(10) "image/jpeg"
var_dump(image_type_to_mime_type(IMAGETYPE_PNG));  // string(9) "image/png"

```

## imageaffine

```php

```

## imageaffinematrixconcat

```php

```

## imageaffinematrixget

```php

```

## imagealphablending

```php

```

## imageantialias

```php

```

## imagearc

```php

```

## imagebmp

```php

```

## imagechar

```php

```

## imagecharup

```php

```

## imagecolorallocate

```php

```

## imagecolorallocatealpha

```php

```

## imagecolorat

```php

```

## imagecolorclosest

```php

```

## imagecolorclosestalpha

```php

```

## imagecolorclosesthwb

```php

```

## imagecolordeallocate

```php

```

## imagecolorexact

```php

```

## imagecolorexactalpha

```php

```

## imagecolormatch

```php

```

## imagecolorresolve

```php

```

## imagecolorresolvealpha

```php

```

## imagecolorset

```php

```

## imagecolorsforindex

```php

```

## imagecolorstotal

```php

```

## imagecolortransparent

```php

```

## imageconvolution

```php

```

## imagecopy

```php

```

## imagecopymerge

```php

```

## imagecopymergegray

```php

```

## imagecopyresampled

```php

```

## imagecopyresized

```php

```

## imagecreate

```php

```

## imagecreatefrombmp

```php

```

## imagecreatefromgd2

```php

```

## imagecreatefromgd2part

```php

```

## imagecreatefromgd

```php

```

## imagecreatefromgif

```php

```

## imagecreatefromjpeg

```php

```

## imagecreatefrompng

```php

```

## imagecreatefromstring

```php

```

## imagecreatefromwbmp

```php

```

## imagecreatefromwebp

```php

```

## imagecreatefromxbm

```php

```

## imagecreatefromxpm

```php

```

## imagecreatetruecolor

```php

```

## imagecrop

```php

```

## imagecropauto

```php

```

## imagedashedline

```php

```

## imagedestroy

```php

```

## imageellipse

```php

```

## imagefill

```php

```

## imagefilledarc

```php

```

## imagefilledellipse

```php

```

## imagefilledpolygon

```php

```

## imagefilledrectangle

```php

```

## imagefilltoborder

```php

```

## imagefilter

```php

```

## imageflip

```php

```

## imagefontheight

```php

```

## imagefontwidth

```php

```

## imageftbbox

```php

```

## imagefttext

```php

```

## imagegammacorrect

```php

```

## imagegd2

```php

```

## imagegd

```php

```

## imagegetclip

```php

```

## imagegif

```php

```

## imagegrabscreen

```php

```

## imagegrabwindow

```php

```

## imageinterlace

```php

```

## imageistruecolor

```php

```

## imagejpeg

```php

```

## imagelayereffect

```php

```

## imageline

```php

```

## imageloadfont

```php

```

## imageopenpolygon

```php

```

## imagepalettecopy

```php

```

## imagepalettetotruecolor

```php

```

## imagepng

```php

```

## imagepolygon

```php

```

## imagepsbbox

```php

```

## imagepsencodefont

```php

```

## imagepsextendfont

```php

```

## imagepsfreefont

```php

```

## imagepsloadfont

```php

```

## imagepsslantfont

```php

```

## imagepstext

```php

```

## imagerectangle

```php

```

## imageresolution

```php

```

## imagerotate

```php

```

## imagesavealpha

```php

```

## imagescale

```php

```

## imagesetbrush

```php

```

## imagesetclip

```php

```

## imagesetinterpolation

```php

```

## imagesetpixel

```php

```

## imagesetstyle

```php

```

## imagesetthickness

```php

```

## imagesettile

```php

```

## imagestring

```php

```

## imagestringup

```php

```

## imagesx

```php

```

## imagesy

```php

```

## imagetruecolortopalette

```php

```

## imagettfbbox

```php

```

## imagettftext

```php

```

## imagetypes

```php

```

## imagewbmp

```php

```

## imagewebp

```php

```

## imagexbm

```php

```

## iptcembed

```php

```

## iptcparse

```php

```

## jpeg2wbmp

```php

```

## png2wbmp

```php

```

