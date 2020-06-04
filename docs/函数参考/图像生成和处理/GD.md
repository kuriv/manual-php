# GD

* [gd_info - 获取当前安装的 GD 库的信息](#gdinfo)
* [getimagesize - 获取指定的图像大小](#getimagesize)
* [getimagesizefromstring - 从指定的字符串中获取图像的大小信息](#getimagesizefromstring)
* [image_type_to_extension - 获取指定的图像类型的文件后缀](#imagetypetoextension)
* [image_type_to_mime_type - 获取指定的图像类型的 MIME 类型](#imagetypetomimetype)

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
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
var_dump(imagechar($image, 5, 0, 0, 'A', imagecolorallocate($image, 0, 0, 0))); // bool(true)

```

## imagecharup

```php

```

## imagecolorallocate

```php
<?php

$image = imagecreate(100, 100);
var_dump(imagecolorallocate($image, 255, 255, 255)); // int(0)
var_dump(imagecolorallocate($image, 100, 100, 100)); // int(1)
var_dump(imagecolorallocate($image, 0, 0, 0));       // int(2)

```

## imagecolorallocatealpha

```php
<?php

$image = imagecreate(100, 100);
var_dump(imagecolorallocatealpha($image, 255, 255, 255, 127)); // int(0)
var_dump(imagecolorallocatealpha($image, 100, 100, 100, 50));  // int(1)
var_dump(imagecolorallocatealpha($image, 0, 0, 0, 0));         // int(2)

```

## imagecolorat

```php
<?php

var_dump(imagecolorat(imagecreatefromjpeg(__DIR__ . '/example.jpg'), 100, 100));

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
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
var_dump(imagecolorsforindex($image, imagecolorat($image, 100, 100)));

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
<?php

var_dump(imagecreate(100, 100)); // resource(4) of type (gd)

```

## imagecreatefrombmp

```php
<?php

var_dump(imagecreatefrombmp(__DIR__ . '/example.bmp'));

```

## imagecreatefromgd2

```php
<?php

var_dump(imagecreatefromgd2(__DIR__ . '/example.gd2'));

```

## imagecreatefromgd2part

```php
<?php

var_dump(imagecreatefromgd2part(__DIR__ . '/example.gd2', 50, 50, 100, 100));

```

## imagecreatefromgd

```php
<?php

var_dump(imagecreatefromgd(__DIR__ . '/example.gd'));

```

## imagecreatefromgif

```php
<?php

var_dump(imagecreatefromgif(__DIR__ . '/example.gif')); // resource(5) of type (gd)

```

## imagecreatefromjpeg

```php
<?php

var_dump(imagecreatefromjpeg(__DIR__ . '/example.jpg')); // resource(5) of type (gd)

```

## imagecreatefrompng

```php
<?php

var_dump(imagecreatefrompng(__DIR__ . '/example.png')); // resource(5) of type (gd)

```

## imagecreatefromstring

```php
<?php

var_dump(imagecreatefromstring(file_get_contents(__DIR__ . '/example.jpg')));           // resource(6) of type (gd)
var_dump(imagecreatefromstring(file_get_contents('https://github.com/fluidicon.png'))); // resource(8) of type (gd)

```

## imagecreatefromwbmp

```php
<?php

var_dump(imagecreatefromwbmp(__DIR__ . '/example.wbmp'));

```

## imagecreatefromwebp

```php
<?php

var_dump(imagecreatefromwebp(__DIR__ . '/example.webp'));

```

## imagecreatefromxbm

```php
<?php

var_dump(imagecreatefromxbm(__DIR__ . '/example.xbm'));

```

## imagecreatefromxpm

```php
<?php

var_dump(imagecreatefromxpm(__DIR__ . '/example.xpm'));

```

## imagecreatetruecolor

```php
<?php

var_dump(imagecreatetruecolor(100, 100)); // resource(4) of type (gd)

```

## imagecrop

```php
<?php

var_dump(imagecrop(imagecreatefromjpeg(__DIR__ . '/example.jpg'), ['x' => 0, 'y' => 0, 'width' => 100, 'height' => 100])); // resource(6) of type (gd)

```

## imagecropauto

```php
<?php

var_dump(imagecropauto(imagecreatefromjpeg(__DIR__ . '/example.jpg'), IMG_CROP_DEFAULT)); // resource(6) of type (gd)

```

## imagedashedline

```php

```

## imagedestroy

```php
<?php

var_dump(imagedestroy(imagecreate(100, 100))); // bool(true)

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
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
var_dump(imageflip($image, IMG_FLIP_HORIZONTAL)); // bool(true)
var_dump(imageflip($image, IMG_FLIP_VERTICAL));   // bool(true)
var_dump(imageflip($image, IMG_FLIP_BOTH));       // bool(true)

```

## imagefontheight

```php
<?php

var_dump(imagefontheight(1)); // int(8)
var_dump(imagefontheight(2)); // int(13)
var_dump(imagefontheight(3)); // int(13)

```

## imagefontwidth

```php
<?php

var_dump(imagefontwidth(1)); // int(5)
var_dump(imagefontwidth(2)); // int(6)
var_dump(imagefontwidth(3)); // int(7)

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
<?php

var_dump(imagesx(imagecreate(100, 100))); // int(100)

```

## imagesy

```php
<?php

var_dump(imagesy(imagecreate(100, 100))); // int(100)

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
<?php

var_dump(imagetypes());

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

