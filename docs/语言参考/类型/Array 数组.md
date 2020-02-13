# Array 数组

可以用 `array()` 语言结构来新建一个数组。它接受任意数量用逗号分隔的键值对。最后一个数组单元之后的逗号可以省略。

```php
<?php

$foo = array(2, 4, 5);
$bar = array(
    'foo' => 'cat',
    'bar' => 'dog'
);

```

还可以使用短数组定义语法，用 `[]` 替代 `array()` 。

```php
<?php

$foo = [2, 4, 5];
$bar = [
    'foo' => 'cat',
    'bar' => 'dog'
];

```

数组的键名可以是整型或者字符串。数组的值可以是任意类型。

此外数组的键会有如下的强制转换：

* 包含有合法整型值的字符串会被转换为整型，例如键名 "8" 实际会被储存为 8 ，但是 "08" 则不会强制转换，因为其不是一个合法的十进制数值。
* 浮点类型也会被转换为整型，意味着其小数部分会被舍去，例如键名 8.7 实际会被储存为 8 。
* 布尔类型也会被转换成整型，即键名 `true` 实际会被储存为 1 ，而键名 `false` 会被储存为 0 。
* `NULL` 会被转换为空字符串，即键名 `NULL` 实际会被储存为 "" 。
* 数组和对象不能被用为键名，坚持这么做会导致警告。

如果在数组定义中多个单元都使用了同一个键名，则只使用了最后一个，之前的都被覆盖了。

```php
<?php

$foo = [
    1    => 'foo',
    '1'  => 'bar',
    1.5  => 'baz',
    true => 'qux'
];
var_dump($foo); // array(1) { [1]=> string(3) "qux" }

```

如果对给出的值没有指定键名，则取当前最大的整数索引值，新的键名将是该值加一。如果指定的键名已经有了值，则该值会被覆盖。

```php
<?php

$foo = ['foo', 'bar', 6 => 'baz', 'qux'];
var_dump($foo); // array(4) { [0]=> string(3) "foo" [1]=> string(3) "bar" [6]=> string(3) "baz" [7]=> string(3) "qux" }

```

可以用直接对函数或方法调用的结果进行数组解引用。

```php
<?php

/**
 * Return an array.
 *
 * @param  void
 * @return array
 */
function foo(): array
{
    return [2, 4, 5];
}

var_dump(foo()[1]); // int(4)

```

要修改数组中的某个键值，通过其键名给该单元赋一个新值。

```php
<?php

$foo = [
    'foo' => 'cat',
    'bar' => 'dog'
];
$foo['bar'] = 'cat';
var_dump($foo); // array(2) { ["foo"]=> string(3) "cat" ["bar"]=> string(3) "cat" }

```

也可以省略键名，在这种情况下给变量名加上一对空的方括号 `[]` 。

```php
<?php

$foo = [
    'foo' => 'cat',
    'bar' => 'dog'
];
$foo[] = 'bird';
var_dump($foo); // array(3) { ["foo"]=> string(3) "cat" ["bar"]=> string(3) "dog" [0]=> string(4) "bird" }

```

要删除某键值对，对其调用 `unset()` 函数。

```php
<?php

$foo = [
    'foo' => 'cat',
    'bar' => 'dog'
];
unset($foo['foo']);
var_dump($foo); // array(1) { ["bar"]=> string(3) "dog" }

```

最大整数键名不一定当前就在数组中，它只要在上次数组重新生成索引后曾经存在过就行了。

```php
<?php

$foo = [1, 2, 3, 4, 5];
var_dump($foo); // array(5) { [0]=> int(1) [1]=> int(2) [2]=> int(3) [3]=> int(4) [4]=> int(5) }

foreach ($foo as $key => $value) {
    unset($foo[$key]);
}
var_dump($foo); // array(0) { }

$foo[] = 6;
var_dump($foo); // array(1) { [5]=> int(6) }

$foo = array_values($foo);
$foo[] = 7;
var_dump($foo); // array(2) { [0]=> int(6) [1]=> int(7) }

```

直接改变数组的值可以通过引用传递来做到。

```php
<?php

$foo = [2, 4, 5];
foreach ($foo as &$value) {
    $value += 1;
}
unset($value);
var_dump($foo); // array(3) { [0]=> int(3) [1]=> int(5) [2]=> int(6) }

```

转换为数组：

```php
<?php

class Foo
{
    //
}

class Bar
{
    /**
     * Public property.
     *
     * @var string
     */
    public string $public = 'public';

    /**
     * Protected property.
     *
     * @var string
     */
    protected string $protected = 'protected';

    /**
     * Private property.
     *
     * @var null
     */
    private $private;
}

var_dump((array) null);    // array(0) { }
var_dump((array) true);    // array(1) { [0]=> bool(true) }
var_dump((array) false);   // array(1) { [0]=> bool(false) }
var_dump((array) 0);       // array(1) { [0]=> int(0) }
var_dump((array) 1);       // array(1) { [0]=> int(1) }
var_dump((array) 1.001);   // array(1) { [0]=> float(1.001) }
var_dump((array) 'foo');   // array(1) { [0]=> string(3) "foo" }
var_dump((array) new Foo); // array(0) { }
var_dump((array) new Bar); // array(3) { ["public"]=> string(6) "public" ["\0*\0protected"]=> string(9) "protected" ["\0Bar\0private"]=> NULL }

```

