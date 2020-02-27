# JSON

* [json_decode - 对 JSON 格式的字符串进行解码](#jsondecode)
* [json_encode - 对变量进行 JSON 编码](#jsonencode)
* [json_last_error_msg - 返回最后一个 json_decode() 或 json_encode() 调用的错误字符串](#jsonlasterrormsg)
* [json_last_error - 返回最后发生的错误](#jsonlasterror)

## json_decode

```php
<?php

var_dump(json_decode('{"foo":2,"bar":5}'));       // object(stdClass)#1 (2) { ["foo"]=> int(2) ["bar"]=> int(5) }
var_dump(json_decode('{"foo":2,"bar":5}', true)); // array(2) { ["foo"]=> int(2) ["bar"]=> int(5) }

```

## json_encode

```php
<?php

var_dump(json_encode(['foo' => 2, 'bar' => 5])); // string(17) "{"foo":2,"bar":5}"

```

## json_last_error_msg

```php
<?php

var_dump(json_last_error_msg());

```

## json_last_error

```php
<?php

var_dump(json_last_error());

```

