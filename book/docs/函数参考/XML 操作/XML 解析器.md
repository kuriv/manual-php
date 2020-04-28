# XML 解析器

* [utf8_decode - 将用 UTF-8 方式编码的 ISO-8859-1 字符串转换成单字节的 ISO-8859-1 字符串](#utf8decode)
* [utf8_encode - 将 ISO-8859-1 编码的字符串转换为 UTF-8 编码](#utf8encode)
* [xml_error_string - 获取 XML 解析器的错误字符串](#xmlerrorstring)
* [xml_get_current_byte_index - 获取 XML 解析器的当前字节索引](#xmlgetcurrentbyteindex)
* [xml_get_current_column_number - 获取 XML 解析器的当前列号](#xmlgetcurrentcolumnnumber)
* [xml_get_current_line_number - 获取 XML 解析器的当前行号](#xmlgetcurrentlinenumber)
* [xml_get_error_code - 获取 XML 解析器错误代码](#xmlgeterrorcode)
* [xml_parse_into_struct - 将 XML 数据解析到数组中](#xmlparseintostruct)
* [xml_parse - 开始解析一个 XML 文档](#xmlparse)
* [xml_parser_create_ns - 生成一个支持命名空间的 XML 解析器](#xmlparsercreatens)
* [xml_parser_create - 建立一个 XML 解析器](#xmlparsercreate)
* [xml_parser_free - 释放指定的 XML 解析器](#xmlparserfree)
* [xml_parser_get_option - 从 XML 解析器获取选项设置信息](#xmlparsergetoption)
* [xml_parser_set_option - 为指定 XML 解析进行选项设置](#xmlparsersetoption)
* [xml_set_character_data_handler - 建立字符数据处理器](#xmlsetcharacterdatahandler)
* [xml_set_default_handler - 建立默认处理器](#xmlsetdefaulthandler)
* [xml_set_element_handler - 建立起始和终止元素处理器](#xmlsetelementhandler)
* [xml_set_end_namespace_decl_handler - 建立终止命名空间声明处理器](#xmlsetendnamespacedeclhandler)
* [xml_set_external_entity_ref_handler - 建立外部实体指向处理器](#xmlsetexternalentityrefhandler)
* [xml_set_notation_decl_handler - 建立注释声明处理器](#xmlsetnotationdeclhandler)
* [xml_set_object - 在对象中使用 XML 解析器](#xmlsetobject)
* [xml_set_processing_instruction_handler - 建立处理指令处理器](#xmlsetprocessinginstructionhandler)
* [xml_set_start_namespace_decl_handler - 建立起始命名空间声明处理器](#xmlsetstartnamespacedeclhandler)
* [xml_set_unparsed_entity_decl_handler - 建立未解析实体定义声明处理器](#xmlsetunparsedentitydeclhandler)

## utf8_decode

```php
<?php

var_dump(utf8_decode("\x66\x6f\x6f")); // string(3) "foo"

```

## utf8_encode

```php
<?php

var_dump(utf8_encode('foo')); // string(3) "foo"

```

## xml_error_string

```php
<?php

var_dump(xml_error_string(xml_get_error_code(xml_parser_create()))); // string(8) "No error"

```

## xml_get_current_byte_index

```php
<?php

var_dump(xml_get_current_byte_index(xml_parser_create())); // int(0)

```

## xml_get_current_column_number

```php
<?php

var_dump(xml_get_current_column_number(xml_parser_create())); // int(1)

```

## xml_get_current_line_number

```php
<?php

var_dump(xml_get_current_line_number(xml_parser_create())); // int(1)

```

## xml_get_error_code

```php
<?php

var_dump(xml_get_error_code(xml_parser_create())); // int(0)

```

## xml_parse_into_struct

```php
<?php

$parser = xml_parser_create();
$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
              <body>Here is some text.</body>
          </document>
          XML;
$array = [];
var_dump(xml_parse_into_struct($parser, $xml, $array)); // int(1)
var_dump($array);                                       // array(6) { [0]=> array(4) { ["tag"]=> string(8) "DOCUMENT" ["type"]=> string(4) "open" ["level"]=> int(1) ["value"]=> string(5) " " } [1]=> array(4) { ["tag"]=> string(5) "TITLE" ["type"]=> string(8) "complete" ["level"]=> int(2) ["value"]=> string(3) "XML" } [2]=> array(4) { ["tag"]=> string(8) "DOCUMENT" ["value"]=> string(5) " " ["type"]=> string(5) "cdata" ["level"]=> int(1) } [3]=> array(4) { ["tag"]=> string(4) "BODY" ["type"]=> string(8) "complete" ["level"]=> int(2) ["value"]=> string(18) "Here is some text." } [4]=> array(4) { ["tag"]=> string(8) "DOCUMENT" ["value"]=> string(1) " " ["type"]=> string(5) "cdata" ["level"]=> int(1) } [5]=> array(3) { ["tag"]=> string(8) "DOCUMENT" ["type"]=> string(5) "close" ["level"]=> int(1) } }

```

## xml_parse

```php
<?php

$parser = xml_parser_create();
$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
              <body>Here is some text.</body>
          </document>
          XML;
var_dump(xml_parse($parser, $xml)); // int(1)

```

## xml_parser_create_ns

```php
<?php

var_dump(xml_parser_create_ns()); // resource(4) of type (xml)

```

## xml_parser_create

```php
<?php

var_dump(xml_parser_create()); // resource(4) of type (xml)

```

## xml_parser_free

```php
<?php

var_dump(xml_parser_free(xml_parser_create())); // bool(true)

```

## xml_parser_get_option

```php
<?php

var_dump(xml_parser_get_option(xml_parser_create(), XML_OPTION_CASE_FOLDING));
var_dump(xml_parser_get_option(xml_parser_create(), XML_OPTION_SKIP_TAGSTART));
var_dump(xml_parser_get_option(xml_parser_create(), XML_OPTION_SKIP_WHITE));
var_dump(xml_parser_get_option(xml_parser_create(), XML_OPTION_TARGET_ENCODING));

```

## xml_parser_set_option

```php
<?php

var_dump(xml_parser_set_option(xml_parser_create(), XML_OPTION_CASE_FOLDING, 1));          // bool(true)
var_dump(xml_parser_set_option(xml_parser_create(), XML_OPTION_SKIP_TAGSTART, 0));         // bool(true)
var_dump(xml_parser_set_option(xml_parser_create(), XML_OPTION_SKIP_WHITE, 0));            // bool(true)
var_dump(xml_parser_set_option(xml_parser_create(), XML_OPTION_TARGET_ENCODING, 'UTF-8')); // bool(true)

```

## xml_set_character_data_handler

```php
<?php

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    //
}

var_dump(xml_set_character_data_handler(xml_parser_create(), 'foo')); // bool(true)

```

## xml_set_default_handler

```php
<?php

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    //
}

var_dump(xml_set_default_handler(xml_parser_create(), 'foo')); // bool(true)

```

## xml_set_element_handler

```php
<?php

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    //
}

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function bar()
{
    //
}

var_dump(xml_set_element_handler(xml_parser_create(), 'foo', 'bar')); // bool(true)

```

## xml_set_end_namespace_decl_handler

```php
<?php

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    //
}

var_dump(xml_set_end_namespace_decl_handler(xml_parser_create(), 'foo')); // bool(true)

```

## xml_set_external_entity_ref_handler

```php
<?php

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    //
}

var_dump(xml_set_external_entity_ref_handler(xml_parser_create(), 'foo')); // bool(true)

```

## xml_set_notation_decl_handler

```php
<?php

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    //
}

var_dump(xml_set_notation_decl_handler(xml_parser_create(), 'foo')); // bool(true)

```

## xml_set_object

```php
<?php

class Foo
{
    //
}

var_dump(xml_set_object(xml_parser_create(), new Foo)); // bool(true)

```

## xml_set_processing_instruction_handler

```php
<?php

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    //
}

var_dump(xml_set_processing_instruction_handler(xml_parser_create(), 'foo')); // bool(true)

```

## xml_set_start_namespace_decl_handler

```php
<?php

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    //
}

var_dump(xml_set_start_namespace_decl_handler(xml_parser_create(), 'foo')); // bool(true)

```

## xml_set_unparsed_entity_decl_handler

```php
<?php

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    //
}

var_dump(xml_set_unparsed_entity_decl_handler(xml_parser_create(), 'foo')); // bool(true)

```