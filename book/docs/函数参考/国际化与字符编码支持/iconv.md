# iconv

* [iconv_get_encoding - 获取 iconv 扩展的内部配置变量](#iconvgetencoding)
* [iconv_mime_decode_headers - 一次性解码多个 MIME 头字段](#iconvmimedecodeheaders)
* [iconv_mime_decode - 解码一个 MIME 头字段](#iconvmimedecode)
* [iconv_mime_encode - 编码一个 MIME 头字段](#iconvmimeencode)
* [iconv_set_encoding - 为字符编码转换设定当前设置](#iconvsetencoding)
* [iconv_strlen - 返回字符串的字符数统计](#iconvstrlen)
* [iconv_strpos - 查找字符串中指定字符串出现的位置](#iconvstrpos)
* [iconv_strrpos - 查找字符串中指定字符串最后出现的位置](#iconvstrrpos)
* [iconv_substr - 截取字符串的部分](#iconvsubstr)
* [iconv - 字符串按要求的字符编码来转换](#iconv)
* [ob_iconv_handler - 以输出缓冲处理程序转换字符编码](#obiconvhandler)

## iconv_get_encoding

```php
<?php

var_dump(iconv_get_encoding());
var_dump(iconv_get_encoding('all'));
var_dump(iconv_get_encoding('input_encoding'));
var_dump(iconv_get_encoding('output_encoding'));
var_dump(iconv_get_encoding('internal_encoding'));

```

## iconv_mime_decode_headers

```php
<?php

var_dump(iconv_mime_decode_headers('Subject: =?UTF-8?B?UHLDvGZ1bmcgUHLDvGZ1bmc=?=')); // array(1) { ["Subject"]=> string(17) "Prüfung Prüfung" }

```

## iconv_mime_decode

```php
<?php

var_dump(iconv_mime_decode('Subject: =?UTF-8?B?UHLDvGZ1bmcgUHLDvGZ1bmc=?=')); // string(26) "Subject: Prüfung Prüfung"

```

## iconv_mime_encode

```php
<?php

var_dump(iconv_mime_encode('Subject', 'Prüfung Prüfung')); // string(45) "Subject: =?UTF-8?B?UHLDvGZ1bmcgUHLDvGZ1bmc=?="

```

## iconv_set_encoding

```php
<?php

var_dump(iconv_set_encoding('all', 'UTF-8'));

```

## iconv_strlen

```php
<?php

var_dump(iconv_strlen('€'));
var_dump(iconv_strlen('foo'));

```

## iconv_strpos

```php
<?php

var_dump(iconv_strpos('foo', 'a'));     // bool(false)
var_dump(iconv_strpos('foo', 'o'));     // int(1)
var_dump(iconv_strpos('foo', 'O'));     // bool(false)
var_dump(iconv_strpos('foo', 'o', 1));  // int(1)
var_dump(iconv_strpos('foo', 'o', 2));  // int(2)
var_dump(iconv_strpos('foo', 'o', -1)); // int(2)
var_dump(iconv_strpos('foo', 'oo'));    // int(1)
var_dump(iconv_strpos('foo', 'oa'));    // bool(false)

```

## iconv_strrpos

```php
<?php

var_dump(iconv_strrpos('foo', 'a'));     // bool(false)
var_dump(iconv_strrpos('foo', 'O'));     // bool(false)
var_dump(iconv_strrpos('foo', 'o'));     // int(2)
var_dump(iconv_strrpos('foo', 'f'));     // int(0)
var_dump(iconv_strrpos('foo', 'oo'));    // int(1)

```

## iconv_substr

```php
<?php

var_dump(iconv_substr('foo', 0));      // string(3) "foo"
var_dump(iconv_substr('foo', 1));      // string(2) "oo"
var_dump(iconv_substr('foo', 1, 1));   // string(1) "o"
var_dump(iconv_substr('foo', 0, -2));  // string(1) "f"
var_dump(iconv_substr('foo', -2));     // string(2) "oo"
var_dump(iconv_substr('foo', -2, 1));  // string(1) "o"
var_dump(iconv_substr('foo', -3, -2)); // string(3) "foo"

```

## iconv

```php
<?php

var_dump(iconv('UTF-8', 'ISO-8859-1//TRANSLIT', '€')); // string(3) "EUR"
var_dump(iconv('UTF-8', 'ISO-8859-1//IGNORE', '€'));   // string(0) ""

```

## ob_iconv_handler

```php
<?php

var_dump(ob_start('ob_iconv_handler')); // bool(true)

```

