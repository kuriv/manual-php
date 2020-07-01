# GD

* [gd_info - 获取当前安装的 GD 库的信息](#gdinfo)
* [getimagesize - 获取指定的图像大小](#getimagesize)
* [getimagesizefromstring - 从指定的字符串中获取图像的大小信息](#getimagesizefromstring)
* [image_type_to_extension - 获取指定的图像类型的文件后缀](#imagetypetoextension)
* [image_type_to_mime_type - 获取指定的图像类型的 MIME 类型](#imagetypetomimetype)
* imageaffine - 返回经过仿射变换后的图像，剪切区域可选
* imageaffinematrixconcat - Concatenate two affine transformation matrices
* imageaffinematrixget - Get an affine transformation matrix
* [imagealphablending - 设定图像的混色模式](#imagealphablending)
* [imageantialias - 是否使用抗锯齿功能](#imageantialias)
* [imagearc - 画椭圆弧](#imagearc)
* [imagebmp - 将 BMP 图像输出到浏览器或文件](#imagebmp)
* [imagechar - 水平地画一个字符](#imagechar)
* [imagecharup - 垂直地画一个字符](#imagecharup)
* [imagecolorallocate - 为一幅图像分配颜色](#imagecolorallocate)
* [imagecolorallocatealpha - 为一幅图像分配颜色和透明度](#imagecolorallocatealpha)
* [imagecolorat - 取得某像素的颜色索引值](#imagecolorat)
* [imagecolorclosest - 取得与指定的颜色最接近的颜色的索引值](#imagecolorclosest)
* [imagecolorclosestalpha - 取得与指定的颜色加透明度最接近的颜色](#imagecolorclosestalpha)
* [imagecolorclosesthwb - 取得与给定颜色最接近的色度的黑白色的索引](#imagecolorclosesthwb)
* [imagecolordeallocate - 取消图像颜色的分配](#imagecolordeallocate)
* [imagecolorexact - 取得指定颜色的索引值](#imagecolorexact)
* [imagecolorexactalpha - 取得指定的颜色加透明度的索引值](#imagecolorexactalpha)
* imagecolormatch - 使一个图像中调色板版本的颜色与真彩色版本更能匹配
* [imagecolorresolve - 取得指定颜色的索引值或有可能得到的最接近的替代值](#imagecolorresolve)
* [imagecolorresolvealpha - 取得指定颜色加透明度的索引值或有可能得到的最接近的替代值](#imagecolorresolvealpha)
* [imagecolorset - 给指定调色板索引设定颜色](#imagecolorset)
* [imagecolorsforindex - 取得某索引的颜色](#imagecolorsforindex)
* [imagecolorstotal - 取得一幅图像的调色板中颜色的数目](#imagecolorstotal)
* [imagecolortransparent - 将某个颜色定义为透明色](#imagecolortransparent)
* imageconvolution - 申请一个 3x3 的卷积矩阵
* [imagecopy - 拷贝图像的一部分](#imagecopy)
* [imagecopymerge - 拷贝并合并图像的一部分](#imagecopymerge)
* [imagecopymergegray - 用灰度拷贝并合并图像的一部分](#imagecopymergegray)
* [imagecopyresampled - 重采样拷贝部分图像并调整大小](#imagecopyresampled)
* [imagecopyresized - 拷贝部分图像并调整大小](#imagecopyresized)
* [imagecreate - 新建一个基于调色板的图像](#imagecreate)
* [imagecreatefrombmp - 由文件或 URL 创建一个新图像](#imagecreatefrombmp)
* [imagecreatefromgd2 - 从 GD2 文件或 URL 新建一图像](#imagecreatefromgd2)
* [imagecreatefromgd2part - 从给定的 GD2 文件或 URL 中的部分新建一图像](#imagecreatefromgd2part)
* [imagecreatefromgd - 从 GD 文件或 URL 新建一图像](#imagecreatefromgd)
* [imagecreatefromgif - 由文件或 URL 创建一个新图像](#imagecreatefromgif)
* [imagecreatefromjpeg - 由文件或 URL 创建一个新图像](#imagecreatefromjpeg)
* [imagecreatefrompng - 由文件或 URL 创建一个新图像](#imagecreatefrompng)
* [imagecreatefromstring - 从字符串中的图像流新建一图像](#imagecreatefromstring)
* [imagecreatefromwbmp - 由文件或 URL 创建一个新图像](#imagecreatefromwbmp)
* [imagecreatefromwebp - 由文件或 URL 创建一个新图像](#imagecreatefromwebp)
* [imagecreatefromxbm - 由文件或 URL 创建一个新图像](#imagecreatefromxbm)
* [imagecreatefromxpm - 由文件或 URL 创建一个新图像](#imagecreatefromxpm)
* [imagecreatetruecolor - 新建一个真彩色图像](#imagecreatetruecolor)
* [imagecrop - 将图像裁剪为给定的矩形](#imagecrop)
* [imagecropauto - 使用可用模式之一自动裁剪图像](#imagecropauto)
* [imagedashedline - 画一虚线](#imagedashedline)
* [imagedestroy - 销毁图像](#imagedestroy)
* [imageellipse - 画一个椭圆](#imageellipse)
* [imagefill - 区域填充](#imagefill)
* [imagefilledarc - 画一椭圆弧且填充](#imagefilledarc)
* [imagefilledellipse - 画一椭圆并填充](#imagefilledellipse)
* [imagefilledpolygon - 画一多边形并填充](#imagefilledpolygon)
* [imagefilledrectangle - 画一矩形并填充](#imagefilledrectangle)
* imagefilltoborder - 区域填充到指定颜色的边界为止
* imagefilter - 对图像使用过滤器
* [imageflip - 使用给定模式翻转图像](#imageflip)
* [imagefontheight - 取得字体高度](#imagefontheight)
* [imagefontwidth - 取得字体宽度](#imagefontwidth)
* imageftbbox - 给出一个使用 FreeType 2 字体的文本框
* imagefttext - 使用 FreeType 2 字体将文本写入图像
* imagegammacorrect - 对 GD 图像应用伽马修正
* [imagegd2 - 将 GD2 图像输出到浏览器或文件](#imagegd2)
* [imagegd - 将 GD 图像输出到浏览器或文件](#imagegd)
* [imagegetclip - 获取裁剪矩形](#imagegetclip)
* [imagegif - 输出图像到浏览器或文件](#imagegif)
* [imagegrabscreen - 截取整个屏幕](#imagegrabscreen)
* [imageinterlace - 激活或禁止隔行扫描](#imageinterlace)
* [imageistruecolor - 检查图像是否为真彩色图像](#imageistruecolor)
* [imagejpeg - 输出图像到浏览器或文件](#imagejpeg)
* imagelayereffect - 设定 alpha 混色标志以使用绑定的 libgd 分层效果
* [imageline - 画一条线段](#imageline)
* imageloadfont - 载入新字体
* imageopenpolygon - Draws an open polygon
* imagepalettecopy - 将调色板从一幅图像拷贝到另一幅
* imagepalettetotruecolor - Converts a palette based image to true color
* [imagepng - 以 PNG 格式将图像输出到浏览器或文件](#imagepng)
* [imagepolygon - 画一个多边形](#imagepolygon)
* imagepsbbox - 给出一个使用 PostScript Type1 字体的文本方框
* imagepsencodefont - 改变字体中的字符编码矢量
* imagepsextendfont - 扩充或精简字体
* imagepsfreefont - 释放一个 PostScript Type 1 字体所占用的内存
* imagepsloadfont - 从文件中加载一个 PostScript Type 1 字体
* imagepsslantfont - 倾斜某字体
* imagepstext - 用 PostScript Type1 字体把文本字符串画在图像上
* [imagerectangle - 画一个矩形](#imagerectangle)
* [imageresolution - 获取或设置图像的分辨率](#imageresolution)
* [imagerotate - 用给定角度旋转图像](#imagerotate)
* imagesavealpha - 设置标记以在保存 PNG 图像时保存完整的 alpha 通道信息（与单一透明色相反）
* [imagescale - 使用给定的新宽度和高度缩放图像](#imagescale)
* imagesetbrush - 设定画线用的画笔图像
* [imagesetclip - 设置裁剪矩形](#imagesetclip)
* [imagesetinterpolation - 设置插值方法](#imagesetinterpolation)
* [imagesetpixel - 画一个单一像素](#imagesetpixel)
* [imagesetstyle - 设定画线的风格](#imagesetstyle)
* [imagesetthickness - 设定画线的宽度](#imagesetthickness)
* imagesettile - 设定用于填充的贴图
* [imagestring - 水平地画一行字符串](#imagestring)
* [imagestringup - 垂直地画一行字符串](#imagestringup)
* [imagesx - 取得图像宽度](#imagesx)
* [imagesy - 取得图像高度](#imagesy)
* [imagetruecolortopalette - 将真彩色图像转换为调色板图像](#imagetruecolortopalette)
* imagettfbbox - 取得使用 TrueType 字体的文本的范围
* imagettftext - 用 TrueType 字体向图像写入文本
* [imagetypes - 返回当前 PHP 版本所支持的图像类型](#imagetypes)
* [imagewbmp - 以 WBMP 格式将图像输出到浏览器或文件](#imagewbmp)
* [imagewebp - 将 WebP 格式的图像输出到浏览器或文件](#imagewebp)
* [imagexbm - 将 XBM 图像输出到浏览器或文件](#imagexbm)
* iptcembed - 将二进制 IPTC 数据嵌入到一幅 JPEG 图像中
* iptcparse - 将二进制 IPTC 块解析为单个标记

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
<?php

$image = imagecreate(100, 100);
imagealphablending($image, true);
imagecolorallocate($image, 255, 255, 255);
imagefilledrectangle($image, 30, 30, 70, 70, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imageantialias

```php
<?php

$foo = imagecreatetruecolor(400, 100);
imagecolorallocate($foo, 0, 0, 0);
imageantialias($foo, true);
imageline($foo, 0, 0, 200, 100, imagecolorallocate($foo, 255, 0, 0));
$bar = imagecreate(200, 100);
imagecolorallocate($bar, 0, 0, 0);
imageline($bar, 0, 0, 200, 100, imagecolorallocate($bar, 255, 0, 0));
imagecopymerge($foo, $bar, 200, 0, 0, 0, 200, 100, 100);
header('Content-Type: image/png');
imagepng($foo);

```

## imagearc

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagearc($image, 50, 50, 50, 50, 0, 360, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imagebmp

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
header('Content-Type: image/bmp');
imagebmp($image, __DIR__ . '/example.bmp');
imagebmp($image);

```

## imagechar

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagechar($image, 5, 0, 0, 'A', imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imagecharup

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagecharup($image, 5, 0, 10, 'A', imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

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
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
var_dump(imagecolorclosest($image, 255, 255, 255));

```

## imagecolorclosestalpha

```php
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
var_dump(imagecolorclosestalpha($image, 255, 255, 255, 50));

```

## imagecolorclosesthwb

```php
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
var_dump(imagecolorclosesthwb($image, 255, 255, 255));

```

## imagecolordeallocate

```php
<?php

$image = imagecreate(100, 100);
$white = imagecolorallocate($image, 255, 255, 255);
imagecolordeallocate($image, $white);
$black = imagecolorallocate($image, 0, 0, 0);
header('Content-Type: image/png');
imagepng($image);

```

## imagecolorexact

```php
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
var_dump(imagecolorexact($image, 255, 255, 255));

```

## imagecolorexactalpha

```php
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
var_dump(imagecolorexactalpha($image, 255, 255, 255, 50));

```

## imagecolormatch

```php

```

## imagecolorresolve

```php
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
var_dump(imagecolorresolve($image, 255, 255, 255));

```

## imagecolorresolvealpha

```php
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
var_dump(imagecolorresolvealpha($image, 255, 255, 255, 50));

```

## imagecolorset

```php
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
imagecolorset($image, imagecolorat($image, 100, 100), 255, 255, 255);

```

## imagecolorsforindex

```php
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
var_dump(imagecolorsforindex($image, imagecolorat($image, 100, 100)));

```

## imagecolorstotal

```php
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
var_dump(imagecolorstotal($image));

```

## imagecolortransparent

```php
<?php

$image = imagecreatetruecolor(100, 100);
var_dump(imagecolortransparent($image));

```

## imageconvolution

```php

```

## imagecopy

```php
<?php

$foo = imagecreate(100, 100);
imagecolorallocate($foo, 255, 0, 0);
$bar = imagecreate(100, 100);
imagecolorallocate($bar, 0, 255, 0);
imagecopy($foo, $bar, 50, 0, 0, 0, 50, 100);
header('Content-Type: image/png');
imagepng($foo);

```

## imagecopymerge

```php
<?php

$foo = imagecreate(100, 100);
imagecolorallocate($foo, 255, 0, 0);
$bar = imagecreate(100, 100);
imagecolorallocate($bar, 0, 255, 0);
imagecopymerge($foo, $bar, 50, 0, 0, 0, 50, 100, 100);
header('Content-Type: image/png');
imagepng($foo);

```

## imagecopymergegray

```php
<?php

$foo = imagecreate(100, 100);
imagecolorallocate($foo, 255, 0, 0);
$bar = imagecreate(100, 100);
imagecolorallocate($bar, 0, 255, 0);
imagecopymergegray($foo, $bar, 50, 0, 0, 0, 50, 100, 100);
header('Content-Type: image/png');
imagepng($foo);

```

## imagecopyresampled

```php
<?php

$foo = imagecreate(200, 200);
imagecolorallocate($foo, 255, 0, 0);
$bar = imagecreate(100, 100);
imagecolorallocate($bar, 0, 255, 0);
imagecopyresampled($foo, $bar, 0, 0, 0, 0, 200, 200, 100, 100);
header('Content-Type: image/png');
imagepng($foo);

```

## imagecopyresized

```php
<?php

$foo = imagecreate(200, 200);
imagecolorallocate($foo, 255, 0, 0);
$bar = imagecreate(100, 100);
imagecolorallocate($bar, 0, 255, 0);
imagecopyresized($foo, $bar, 0, 0, 0, 0, 200, 200, 100, 100);
header('Content-Type: image/png');
imagepng($foo);

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
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagedashedline($image, 0, 0, 100, 100, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imagedestroy

```php
<?php

var_dump(imagedestroy(imagecreate(100, 100))); // bool(true)

```

## imageellipse

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imageellipse($image, 50, 50, 50, 50, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imagefill

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagefill($image, 0, 0, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imagefilledarc

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagefilledarc($image, 50, 50, 50, 50, 0, 360, imagecolorallocate($image, 0, 0, 0), IMG_ARC_PIE);
header('Content-Type: image/png');
imagepng($image);

```

## imagefilledellipse

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagefilledellipse($image, 50, 50, 50, 50, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imagefilledpolygon

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagefilledpolygon($image, [20, 30, 50, 10, 80, 30, 70, 85, 30, 85], 5, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imagefilledrectangle

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagefilledrectangle($image, 20, 20, 80, 80, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

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
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagegd2($image, __DIR__ . '/example.gd2');

```

## imagegd

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagegd($image, __DIR__ . '/example.gd');

```

## imagegetclip

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagesetclip($image, 20, 20, 80, 80);
var_dump(imagegetclip($image)); // array(4) { [0]=> int(20) [1]=> int(20) [2]=> int(80) [3]=> int(80) }

```

## imagegif

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
header('Content-Type: image/gif');
imagegif($image);
imagegif($image, __DIR__ . '/example.gif');

```

## imagegrabscreen

```php
<?php

$image = imagegrabscreen();
header('Content-Type: image/png');
imagepng($image);

```

## imageinterlace

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
var_dump(imageinterlace($image));    // int(0)
var_dump(imageinterlace($image, 1)); // int(1)
var_dump(imageinterlace($image, 0)); // int(0)

```

## imageistruecolor

```php
<?php

$image = imagecreate(100, 100);
var_dump(imageistruecolor($image)); // bool(false)

$image = imagecreatetruecolor(100, 100);
var_dump(imageistruecolor($image)); // bool(true)

```

## imagejpeg

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
header('Content-Type: image/jpg');
imagejpeg($image);
imagejpeg($image, __DIR__ . '/example.jpg');

```

## imagelayereffect

```php

```

## imageline

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imageline($image, 0, 0, 100, 100, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

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
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
header('Content-Type: image/png');
imagepng($image);
imagepng($image, __DIR__ . '/example.png');

```

## imagepolygon

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagepolygon($image, [20, 30, 50, 10, 80, 30, 70, 85, 30, 85], 5, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

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
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagerectangle($image, 20, 20, 80, 80, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imageresolution

```php
<?php

$image = imagecreate(100, 100);
var_dump(imageresolution($image));

imageresolution($image, 200);
var_dump(imageresolution($image)); // array(2) { [0]=> int(200) [1]=> int(200) }

imageresolution($image, 50, 100);
var_dump(imageresolution($image)); // array(2) { [0]=> int(50) [1]=> int(100) }

```

## imagerotate

```php
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
$image = imagerotate($image, -90, 0);
header('Content-Type: image/jpg');
imagejpeg($image);

```

## imagesavealpha

```php

```

## imagescale

```php
<?php

$image = imagecreatefromjpeg(__DIR__ . '/example.jpg');
$image = imagescale($image, 100, 100);
header('Content-Type: image/jpg');
imagejpeg($image);

```

## imagesetbrush

```php

```

## imagesetclip

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagesetclip($image, 20, 20, 80, 80);
imageline($image, 0, 0, 100, 100, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imagesetinterpolation

```php
<?php

$image = imagecreate(100, 100);
var_dump(imagesetinterpolation($image, IMG_MITCHELL)); // bool(true)

```

## imagesetpixel

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagesetpixel($image, 10, 10, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imagesetstyle

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
$red = imagecolorallocate($image, 255, 0, 0);
$green = imagecolorallocate($image, 0, 255, 0);
imagesetstyle($image, [$red, $red, $red, $green, $green, $green]);
imageline($image, 0, 0, 100, 100, IMG_COLOR_STYLED);
header('Content-Type: image/png');
imagepng($image);

```

## imagesetthickness

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagesetthickness($image, 5);
imageline($image, 0, 0, 100, 100, imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imagesettile

```php

```

## imagestring

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagestring($image, 5, 0, 0, 'foo', imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

```

## imagestringup

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagestringup($image, 5, 0, 100, 'foo', imagecolorallocate($image, 0, 0, 0));
header('Content-Type: image/png');
imagepng($image);

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
<?php

$image = imagecreatetruecolor(100, 100);
imagefilledrectangle($image, 0, 0, 100, 100, imagecolorallocate($image, 255, 255, 255));
imagetruecolortopalette($image, false, 255);
header('Content-Type: image/png');
imagepng($image);

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
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagewbmp($image, __DIR__ . '/example.wbmp');

```

## imagewebp

```php
<?php

$image = imagecreatetruecolor(100, 100);
imagecolorallocate($image, 255, 255, 255);
header('Content-Type: image/webp');
imagewebp($image);
imagewebp($image, __DIR__ . '/example.webp');

```

## imagexbm

```php
<?php

$image = imagecreate(100, 100);
imagecolorallocate($image, 255, 255, 255);
imagexbm($image, __DIR__ . '/example.xbm');

```

## iptcembed

```php

```

## iptcparse

```php

```

