# include

`include` 语句包含并运行指定文件。被包含文件先按参数给出的路径寻找，如果没有给出目录（只有文件名）时则按照 `include_path` 指定的目录寻找。如果在 `include_path` 下没找到该文件则 `include` 最后才在调用脚本文件所在的目录和当前工作目录下寻找。如果最后仍未找到文件则 `include` 会发出一条警告。

```php
<?php

include 'example.php';

```

如果定义了路径，不管是绝对路径（在 Windows 下以盘符或者 `\` 开头，在 Unix / Linux 下以 `/` 开头）还是当前目录的相对路径（以 `.` 或者 `..` 开头）， `include_path` 都会被完全忽略。例如一个文件以 `../` 开头，则解析器会在当前目录的父目录下寻找该文件。

```php
<?php

include __DIR__ . '/example.php';

```

当一个文件被包含时，其中所包含的代码继承了 `include` 所在行的变量范围。从该处开始，调用文件在该行处可用的任何变量在被调用的文件中也都可用。不过所有在包含文件中定义的函数和类都具有全局作用域。

```php
<?php

$foo = 'foo';
include __DIR__ . '/example.php';
// string(3) "foo"

```

上例中的 `example.php` 文件内容：

```php
<?php

var_dump($foo);

```

如果 `include` 出现于调用文件中的一个函数里，则被调用的文件中所包含的所有代码将表现得如同它们是在该函数内部定义的一样。所以它将遵循该函数的变量范围。

```php
<?php

/**
 * Include files in functions.
 *
 * @param  void
 * @return string
 */
function foo(): string
{
    include __DIR__ . '/example.php';
    return $foo;
}

var_dump(foo()); // string(3) "foo"
var_dump($foo);  // NULL

```

上例中的 `example.php` 文件内容：

```php
<?php

$foo = 'foo';

```

在失败时 `include` 返回 `false` 并且发出警告。成功的包含则返回 1 ，除非在包含文件中另外给出了返回值。

```php
<?php

$foo = include __DIR__ . '/foo.php';
var_dump($foo); // string(3) "foo"

$bar = include __DIR__ . '/bar.php';
var_dump($bar); // int(1)

```

上例中的 `foo.php` 文件内容：

```php
<?php

$foo = 'foo';
return $foo;

```

上例中的 `bar.php` 文件内容：

```php
<?php

$bar = 'bar';

```

