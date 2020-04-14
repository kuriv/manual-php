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



