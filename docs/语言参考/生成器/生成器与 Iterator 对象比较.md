# 生成器与 Iterator 对象比较

生成器的主要优点是简单。与实现 `Iterator` 类相比，编写更少的代码 ，并且代码通常更具可读性。然而，这种灵活性需要付出代价，生成器只是仅向前迭代器，一旦迭代开始就无法倒回。这也意味着同一个生成器不能多次迭代，生成器需要通过再次调用生成器函数来重建，或者通过 `clone` 关键字克隆。

```php
<?php

/**
 * Yielding test values.
 *
 * @param  void
 * @return void
 */
function foo()
{
    $handle = fopen(__DIR__ . '/example.txt', 'r');
    while ($line = fgets($handle)) {
        yield trim($line);
    }
}

class Foo implements Iterator
{
    /**
     * Store a handle.
     *
     * @var resource
     */
    private $property;

    /**
     * Store the current line content.
     *
     * @var string
     */
    private $line;

    /**
     * Store the current line number.
     *
     * @var int
     */
    private $number;

    /**
     * Store a handle to the property.
     *
     * @param  void
     * @return void
     */
    public function __construct()
    {
        $this->property = fopen(__DIR__ . '/example.txt', 'r');
    }

    /**
     * Return the current line content of the specified property.
     *
     * @param  void
     * @return mixed
     */
    public function current()
    {
        return $this->line;
    }

    /**
     * Save the next line content and line number to the specified property and advance the file pointer.
     *
     * @param  void
     * @return void
     */
    public function next()
    {
        if ($this->line !== false) {
            $this->line = fgets($this->property);
            $this->number++;
        }
    }

    /**
     * Return the current line number of the specified property.
     *
     * @param  void
     * @return mixed
     */
    public function key()
    {
        return $this->number;
    }

    /**
     * Return the validity of the current position of the specified property.
     *
     * @param  void
     * @return bool
     */
    public function valid(): bool
    {
        return $this->line !== false;
    }

    /**
     * Set the file pointer of the specified property to the first line and rewind the value of the specified property.
     *
     * @param  void
     * @return void
     */
    public function rewind()
    {
        fseek($this->property, 0);
        $this->line = fgets($this->property);
        $this->number = 0;
    }
}

$foo = foo();
foreach ($foo as $value) {
    var_dump($value);
}
// string(3) "foo"
// string(3) "bar"
// string(3) "baz"
// string(3) "qux"

foreach ($foo as $value) {
    var_dump($value);
}
// PHP Fatal error:  Uncaught Exception: Cannot traverse an already closed generator.

$foo = new Foo;
foreach ($foo as $value) {
    var_dump(trim($value));
}
// string(3) "foo"
// string(3) "bar"
// string(3) "baz"
// string(3) "qux"

foreach ($foo as $value) {
    var_dump(trim($value));
}
// string(3) "foo"
// string(3) "bar"
// string(3) "baz"
// string(3) "qux"

```

上例中的 `example.txt` 文件内容：

```
foo
bar
baz
qux
```

