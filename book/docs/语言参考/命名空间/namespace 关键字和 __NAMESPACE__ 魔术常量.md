# namespace 关键字和 \_\_NAMESPACE\_\_ 魔术常量

PHP 支持两种抽象的访问当前命名空间内部元素的方法， `__NAMESPACE__` 魔术常量和 `namespace` 关键字。常量 `__NAMESPACE__` 的值是包含当前命名空间名称的字符串。

```php
<?php

namespace Foo;

var_dump(__NAMESPACE__); // string(3) "Foo"

```

在全局的，不包括在任何命名空间中的代码，它包含一个空的字符串。

```php
<?php

var_dump(__NAMESPACE__); // string(0) ""

```

常量 `__NAMESPACE__` 在动态创建名称时很有用。

```php
<?php

namespace Foo;

class Bar
{
    //
}

/**
 * Return the specified instance.
 *
 * @param  string $name
 * @return \Foo\Bar
 */
function bar(string $name): \Foo\Bar
{
    $bar = __NAMESPACE__ . '\\' . $name;
    return new $bar;
}

var_dump(bar('Bar')); // object(Foo\Bar)#1 (0) { }

```

关键字 `namespace` 可用来显式访问当前命名空间或子命名空间中的元素。它等价于类中的 `self` 操作符。

```php
<?php

namespace Foo;

class Bar
{
    //
}

/**
 * Return the name of the current namespace.
 *
 * @param  void
 * @return string
 */
function bar(): string
{
    return __NAMESPACE__;
}

const BAR = __NAMESPACE__;

var_dump(new namespace\Bar()); // object(Foo\Bar)#1 (0) { }
var_dump(namespace\bar());     // string(3) "Foo"
var_dump(namespace\BAR);       // string(3) "Foo"

```

全局命名空间中的 `namespace` 操作符。

```php
<?php

class Bar
{
    //
}

/**
 * Return the name of the current namespace.
 *
 * @param  void
 * @return string
 */
function bar(): string
{
    return __NAMESPACE__;
}

const BAR = __NAMESPACE__;

var_dump(new namespace\Bar()); // object(Bar)#1 (0) { }
var_dump(namespace\bar());     // string(0) ""
var_dump(namespace\BAR);       // string(0) ""

```

