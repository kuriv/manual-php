# Serializable

自定义序列化的接口。实现此接口的类将不再支持 `__sleep()` 和 `__wakeup()` 。不论何时，只要有实例需要被序列化， `serialize()` 方法都将被调用。它将不会调用 `__destruct()` 或有其他影响，除非程序化地调用此方法。当数据被反序列化时，类将被感知并且调用合适的 `unserialize()` 方法而不是调用 `__construct()` 。如果需要执行标准的构造器，你应该在这个方法中进行处理。

```php
<?php

class Foo implements Serializable
{
    /**
     * Just a test property.
     *
     * @var string
     */
    private string $property;

    /**
     * Initialize the value of the property.
     *
     * @param  void
     * @return void
     */
    public function __construct()
    {
        $this->property = 'foo';
    }

    /**
     * Return the specified property that was serialized.
     *
     * @param  void
     * @return string
     */
    public function serialize(): string
    {
        return serialize($this->property);
    }

    /**
     * Set the value of the specified property.
     *
     * @param  string $data
     * @return void
     */
    public function unserialize($data)
    {
        $this->property = unserialize($data);
    }

    /**
     * Return the specified property.
     *
     * @param  void
     * @return string
     */
    public function method(): string
    {
        return $this->property;
    }
}

$foo = new Foo();
$data = serialize($foo);
var_dump($data);          // string(25) "C:3:"Foo":10:{s:3:"foo";}"

$foo = unserialize($data);
var_dump($foo->method()); // string(3) "foo"

```

