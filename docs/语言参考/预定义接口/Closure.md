# Closure

用于代表匿名函数的类。匿名函数会产生这个类的对象。在过去，这个类被认为是一个实现细节，但现在可以依赖它做一些事情。这个类带有一些方法，允许在匿名函数创建后对其进行更多的控制。

```php
<?php

class Foo
{
    /**
     * Just a test property.
     *
     * @var string
     */
    public static $foo = 'foo';

    /**
     * Just a test property.
     *
     * @var string
     */
    public $bar = 'bar';

    /**
     * Just a test property.
     *
     * @var string
     */
    private static $baz = 'baz';

    /**
     * Just a test property.
     *
     * @var string
     */
    private $qux = 'qux';

    /**
     * Just a test property.
     *
     * @var int
     */
    private $quux = 1;

    /**
     * Return a string.
     *
     * @param  void
     * @return string
     */
    public function method()
    {
        return 'method';
    }
}

/**
 * Return the specified property.
 *
 * @param  void
 * @return string
 */
$foo = function (): string {
    return static::$foo;
};
$method = Closure::bind($foo, new Foo);
var_dump($method());            // string(3) "foo"
$method = $foo->bindTo(new Foo);
var_dump($method());            // string(3) "foo"

/**
 * Return the specified property.
 *
 * @param  void
 * @return string
 */
$bar = function (): string {
    return $this->bar;
};
$method = Closure::bind($bar, new Foo);
var_dump($method());            // string(3) "bar"
$method = $bar->bindTo(new Foo);
var_dump($method());            // string(3) "bar"

/**
 * Return the specified property.
 *
 * @param  void
 * @return string
 */
$baz = function (): string {
    return static::$baz;
};
$method = Closure::bind($baz, new Foo, 'Foo');
var_dump($method());            // string(3) "baz"
$method = $baz->bindTo(new Foo, 'Foo');
var_dump($method());            // string(3) "baz"

/**
 * Return the specified property.
 *
 * @param  void
 * @return string
 */
$qux = function (): string {
    return $this->qux;
};
$method = Closure::bind($qux, new Foo, 'Foo');
var_dump($method());            // string(3) "qux"
$method = $qux->bindTo(new Foo, 'Foo');
var_dump($method());            // string(3) "qux"

/**
 * Return the specified property.
 *
 * @param  void
 * @return string
 */
$quux = function (): int {
    return $this->quux += 5;
};
$quux = $quux->call(new Foo);
var_dump($quux);                // int(6)

$quuz = Closure::fromCallable([new Foo, 'method']);
var_dump($quuz());              // string(6) "method"

```

