# String 字符串

定义一个字符串的最简单的方法是用单引号 `''` 把它包围起来。

```php
<?php

$foo = 'foo';

```

要表达一个单引号自身，需在它的前面加个反斜线 `\` 来转义。要表达一个反斜线自身，则用两个反斜线 `\\` 。其它任何方式的反斜线都会被当成反斜线本身。也就是说如果想使用其它转义序列例如 `\r` 或者 `\n` ，并不代表任何特殊含义，就单纯是这两个字符本身。

```php
<?php

$foo = '\'';
$bar = '\\';

```

如果字符串是包围在双引号 `""` 中， PHP 将对一些特殊的字符进行解析。

```php
<?php

$foo = 'foo';
$bar = "$foo\r\nbar";

```

另一种表达字符串的方法是用 `Heredoc` 句法结构： `<<<` 。在该运算符之后要提供一个标识符，然后换行。接下来是字符串本身，最后要用前面定义的标识符作为结束标志。标识符的命名也要像其它标签一样遵守 PHP 的规则：只能包含字母、数字和下划线，并且必须以字母和下划线作为开头。 `Heredoc` 结构就像是没有使用双引号的双引号字符串，这就是说在 `Heredoc` 结构中单引号不用被转义，但是转义序列还可以使用。变量将被替换，但在 `Heredoc` 结构中含有复杂的变量时要格外小心。

```php
<?php

$foo = 'foo';
$bar = <<<EOT
          $foo
          \r\n
          bar
          EOT;

```

就像 `Heredoc` 结构类似于双引号字符串， `Nowdoc` 结构是类似于单引号字符串的。 `Nowdoc` 结构很像 `Heredoc` 结构，但是 `Nowdoc` 中不进行解析操作。这种结构很适合用于嵌入 PHP 代码或其它大段文本而无需对其中的特殊字符进行转义。一个 `Nowdoc` 结构也和 `Heredoc` 结构用一样的标记 `<<<` ，但是跟在后面的标识符要用单引号括起来，即 `<<<'EOT'` 。 `Heredoc` 结构的所有规则也同样适用于 `Nowdoc` 结构。

```php
<?php

$foo = 'foo';
$bar = <<<'EOT'
           $foo
           \r\n
           bar
           EOT;

```

当 PHP 解析器遇到一个美元符号 `$` 时，它会和其它很多解析器一样，去组合尽量多的标识以形成一个合法的变量名。

```php
<?php

$foo = 'foo';
var_dump("foo bar $foo baz qux"); // string(19) "foo bar foo baz qux"
var_dump("foo bar $foobaz qux");  // string(12) "foo bar  qux"

```

一个数组索引也可以被解析，数组索引要用方括号 `]` 来表示索引结束的边际。

```php
<?php

$foo = ['foo' => 'cat', 'dog', 'bird'];
var_dump("foo bar $foo[foo]baz qux"); // string(18) "foo bar catbaz qux"
var_dump("foo bar $foo[0] baz qux");  // string(19) "foo bar dog baz qux"
var_dump("foo bar $foo[1] baz qux");  // string(20) "foo bar bird baz qux"
var_dump("foo bar $foo[0]baz qux");   // string(18) "foo bar dogbaz qux"
var_dump("foo bar $foo[1]baz qux");   // string(19) "foo bar birdbaz qux"

```

一个对象属性也可被解析，对象属性则是和上述的变量规则相同。

```php
<?php

class Foo
{
    /**
     * Just a test property.
     *
     * @var string
     */
    public string $property = 'foo';
}

$foo = new Foo;
var_dump("foo bar $foo->property baz qux"); // string(19) "foo bar foo baz qux"
var_dump("foo bar $foo->propertybaz qux");  // string(12) "foo bar  qux"

```

复杂语法不是因为其语法复杂而得名，而是因为它可以使用复杂的表达式。只需简单地像在字符串以外的地方那样写出表达式，然后用花括号 `{}` 把它括起来即可。由于 `{` 无法被转义，只有 `$` 紧挨着 `{` 时才会被识别。可以用 `{\$` 来表达 `{$` 。

```php
<?php

$foo = 'foo';
var_dump("foo bar { $foo} baz qux"); // string(22) "foo bar { foo} baz qux"
var_dump("foo bar {$foo} baz qux");  // string(19) "foo bar foo baz qux"
var_dump("foo bar ${foo} baz qux");  // string(19) "foo bar foo baz qux"
var_dump("foo bar {$foo}baz qux");   // string(18) "foo bar foobaz qux"

```

数组索引可以使用复杂语法解析。

```php
<?php

$foo = ['foo' => 'cat', 'dog', 'bird'];
var_dump("foo bar {$foo['foo']}baz qux"); // string(18) "foo bar catbaz qux"
var_dump("foo bar {$foo[0]} baz qux");    // string(19) "foo bar dog baz qux"
var_dump("foo bar {$foo[1]} baz qux");    // string(20) "foo bar bird baz qux"
var_dump("foo bar {$foo[0]}baz qux");     // string(18) "foo bar dogbaz qux"
var_dump("foo bar {$foo[1]}baz qux");     // string(19) "foo bar birdbaz qux"

```

对象属性也可以使用复杂语法解析。

```php
<?php

class Foo
{
    /**
     * Just a test property.
     *
     * @var string
     */
    public string $property = 'foo';
}

$foo = new Foo;
var_dump("foo bar {$foo->property} baz qux"); // string(19) "foo bar foo baz qux"
var_dump("foo bar {$foo->property}baz qux");  // string(18) "foo bar foobaz qux"

```

字符串中的字符可以通过一个从 0 开始的下标，用类似数组结构中的方括号包含对应的数字来访问。

```php
<?php

$foo = 'foo';
var_dump($foo[0]); // string(1) "f"
var_dump($foo[1]); // string(1) "o"
var_dump($foo[2]); // string(1) "o"

```

也可以用类似数组结构中的方括号包含对应的数字来修改。

```php
<?php

$foo = 'foo';
$foo[strlen($foo) - 1] = '0';
var_dump($foo); // string(3) "fo0"

```

字符串下标必须为整数或可转换为整数的字符串，否则会发出警告并转换成 0 。

```php
<?php

$foo = 'foo';
var_dump($foo['1']);          // string(1) "o"
var_dump(isset($foo['1']));   // bool(true)
var_dump($foo['1.0']);        // string(1) "o"
var_dump(isset($foo['1.0'])); // bool(false)
var_dump($foo['x']);          // string(1) "f"
var_dump(isset($foo['x']));   // bool(false)
var_dump($foo['1x']);         // string(1) "o"
var_dump(isset($foo['1x']));  // bool(false)

```

转换为字符串：

```php
<?php

var_dump((string) -10);    // string(3) "-10"
var_dump((string) 0);      // string(1) "0"
var_dump((string) 0.0001); // string(6) "0.0001"
var_dump((string) true);   // string(1) "1"
var_dump((string) false);  // string(0) ""
var_dump((string) 1e7);    // string(8) "10000000"

```

