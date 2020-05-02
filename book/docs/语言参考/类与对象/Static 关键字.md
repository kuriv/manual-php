# Static 关键字

声明类属性或方法为静态，就可以不实例化类而直接访问。静态属性不能通过一个类已实例化的对象来访问（但静态方法可以）。由于静态方法不需要通过对象即可调用，所以伪变量 `$this` 在静态方法中不可用。静态属性不可以由对象运算符 `->` 来访问。用静态方式调用一个非静态方法会导致一个 `E_STRICT` 级别的错误。就像其它所有的 PHP 静态变量一样，静态属性只能被初始化为常数。可以用一个变量来动态调用类，但该变量的值不能为关键字 `self` ， `parent` 或 `static` 。

```php
<?php

class Foo
{
    /**
     * Just a test property.
     *
     * @var string
     */
    public static string $property = 'foo';
}

var_dump(Foo::$property);  // string(3) "foo"

$foo = new Foo();
var_dump($foo::$property); // string(3) "foo"

$foo = 'Foo';
var_dump($foo::$property); // string(3) "foo"

$foo = 'Foo';
$foo = new $foo;
var_dump($foo::$property); // string(3) "foo"

$foo = new Foo();
$foo = new $foo;
var_dump($foo::$property); // string(3) "foo"

```

调用静态方法。

```php
<?php

class Foo
{
    /**
     * Return a string.
     *
     * @param  void
     * @return string
     */
    public static function method(): string
    {
        return 'foo';
    }
}

var_dump(Foo::method());  // string(3) "foo"

$foo = new Foo();
var_dump($foo::method()); // string(3) "foo"

$foo = 'Foo';
var_dump($foo::method()); // string(3) "foo"

$foo = 'Foo';
$foo = new $foo;
var_dump($foo::method()); // string(3) "foo"

$foo = new Foo();
$foo = new $foo;
var_dump($foo::method()); // string(3) "foo"

```

