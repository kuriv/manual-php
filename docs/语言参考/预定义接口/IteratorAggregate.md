# IteratorAggregate

创建外部迭代器的接口。

```php
<?php

class Foo implements IteratorAggregate
{
    /**
     * Just a test property.
     *
     * @var string
     */
    public string $foo = 'foo';

    /**
     * Just a test property.
     *
     * @var string
     */
    public string $bar = 'bar';

    /**
     * Just a test property.
     *
     * @var string
     */
    public string $baz = 'baz';

    /**
     * Just a test property.
     *
     * @var string
     */
    public string $qux = 'qux';

    /**
     * Return an external iterator.
     *
     * @param  void
     * @return ArrayIterator
     */
    public function getIterator(): ArrayIterator
    {
        return new ArrayIterator($this);
    }
}

$foo = new Foo;
foreach ($foo as $key => $value) {
    var_dump("$key => $value");
}
// string(10) "foo => foo"
// string(10) "bar => bar"
// string(10) "baz => baz"
// string(10) "qux => qux"

```

