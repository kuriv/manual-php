# Object 对象

要创建一个新的对象，使用 `new` 语句实例化一个类。

```php
<?php

class Foo
{
    //
}

$foo = new Foo();

```

转换为对象：

```php
<?php

var_dump((object) 'foo');                            // object(stdClass)#1 (1) { ["scalar"]=> string(3) "foo" }
var_dump((object) [2, 4, 5]);                        // object(stdClass)#1 (3) { ["0"]=> int(2) ["1"]=> int(4) ["2"]=> int(5) }
var_dump((object) ['foo' => 'cat', 'bar' => 'dog']); // object(stdClass)#1 (2) { ["foo"]=> string(3) "cat" ["bar"]=> string(3) "dog" }

```

