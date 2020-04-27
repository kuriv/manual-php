# XML 解析器

* [utf8_decode - 将用 UTF-8 方式编码的 ISO-8859-1 字符串转换成单字节的 ISO-8859-1 字符串](#utf8decode)
* [utf8_encode - 将 ISO-8859-1 编码的字符串转换为 UTF-8 编码](#utf8encode)
* [xml_error_string - 获取 XML 解析器的错误字符串](#xmlerrorstring)
* [xml_get_current_byte_index - 获取 XML 解析器的当前字节索引]
* [xml_get_current_column_number - 获取 XML 解析器的当前列号]
* [xml_get_current_line_number - 获取 XML 解析器的当前行号]
* [xml_get_error_code - 获取 XML 解析器错误代码]
* [xml_parse_into_struct - 将 XML 数据解析到数组中]
* [xml_parse - 开始解析一个 XML 文档]
* [xml_parser_create_ns - 生成一个支持命名空间的 XML 解析器](#xmlparsercreatens)
* [xml_parser_create - 建立一个 XML 解析器](#xmlparsercreate)
* [xml_parser_free - 释放指定的 XML 解析器](#xmlparserfree)
* [xml_parser_get_option - 从 XML 解析器获取选项设置信息]
* [xml_parser_set_option - 为指定 XML 解析进行选项设置]
* [xml_set_character_data_handler - 建立字符数据处理器]
* [xml_set_default_handler - 建立默认处理器]
* [xml_set_element_handler - 建立起始和终止元素处理器]
* [xml_set_end_namespace_decl_handler - 建立终止命名空间声明处理器]
* [xml_set_external_entity_ref_handler - 建立外部实体指向处理器]
* [xml_set_notation_decl_handler - 建立注释声明处理器]
* [xml_set_object - 在对象中使用 XML 解析器]
* [xml_set_processing_instruction_handler - 建立处理指令（PI）处理器]
* [xml_set_start_namespace_decl_handler - 建立起始命名空间声明处理器]
* [xml_set_unparsed_entity_decl_handler - 建立未解析实体定义声明处理器]

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

```

## xml_get_current_column_number

```php

```

## xml_get_current_line_number

```php

```

## xml_get_error_code

```php

```

## xml_parse_into_struct

```php

```

## xml_parse

```php

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

```

## xml_set_default_handler

```php

```

## xml_set_element_handler

```php

```

## xml_set_end_namespace_decl_handler

```php

```

## xml_set_external_entity_ref_handler

```php

```

## xml_set_notation_decl_handler

```php

```

## xml_set_object

```php

```

## xml_set_processing_instruction_handler

```php

```

## xml_set_start_namespace_decl_handler

```php

```

## xml_set_unparsed_entity_decl_handler

```php

```