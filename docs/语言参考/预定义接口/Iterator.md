# Iterator

可在内部迭代自己的外部迭代器或类的接口。

```php
<?php

class Foo implements Iterator
{
    /**
     * Store an array.
     *
     * @var array
     */
    private array $property;

    /**
     * Store an array to the property.
     *
     * @param  array $array
     * @return void
     */
    public function __construct(array $array)
    {
        $this->property = $array;
    }

    /**
     * Return the current element of the specified property.
     *
     * @param  void
     * @return int
     */
    public function current(): int
    {
        var_dump(__METHOD__);
        return current($this->property);
    }

    /**
     * Advance the internal pointer of the specified property.
     *
     * @param  void
     * @return void
     */
    public function next()
    {
        var_dump(__METHOD__);
        next($this->property);
    }

    /**
     * Return the current key of the specified property.
     *
     * @param  void
     * @return int
     */
    public function key(): int
    {
        var_dump(__METHOD__);
        return key($this->property);
    }

    /**
     * Return the validity of the current position of the specified property.
     *
     * @param  void
     * @return bool
     */
    public function valid(): bool
    {
        var_dump(__METHOD__);
        return current($this->property) !== false;
    }

    /**
     * Set the internal pointer of the specified property to the first element.
     *
     * @param  void
     * @return void
     */
    public function rewind()
    {
        var_dump(__METHOD__);
        reset($this->property);
    }
}

$foo = new Foo([2, 4, 5]);
foreach ($foo as $key => $value) {
    var_dump("$key => $value");
    echo "\r\n";
}
// string(11) "Foo::rewind"
// string(10) "Foo::valid"
// string(12) "Foo::current"
// string(8) "Foo::key"
// string(6) "0 => 2"

// string(9) "Foo::next"
// string(10) "Foo::valid"
// string(12) "Foo::current"
// string(8) "Foo::key"
// string(6) "1 => 4"

// string(9) "Foo::next"
// string(10) "Foo::valid"
// string(12) "Foo::current"
// string(8) "Foo::key"
// string(6) "2 => 5"

// string(9) "Foo::next"
// string(10) "Foo::valid"

```

