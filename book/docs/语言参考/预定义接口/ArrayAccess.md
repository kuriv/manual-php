# ArrayAccess

提供像访问数组一样访问对象的能力的接口。

```php
<?php

class Foo implements ArrayAccess
{
    /**
     * Store an array.
     *
     * @var array
     */
    private $property;

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
     * Return whether the specified offset of the specified property exists.
     *
     * @param  mixed $offset
     * @return bool
     */
    public function offsetExists($offset): bool
    {
        return isset($this->property[$offset]);
    }

    /**
     * Return the value of the specified offset of the specified property.
     *
     * @param  mixed $offset
     * @return mixed
     */
    public function offsetGet($offset)
    {
        return $this->property[$offset] ?? null;
    }

    /**
     * Set the value of the specified offset of the specified property.
     *
     * @param  mixed $offset
     * @param  mixed $value
     * @return void
     */
    public function offsetSet($offset, $value)
    {
        if (is_null($offset)) {
            $this->property[] = $value;
        } else {
            $this->property[$offset] = $value;
        }
    }

    /**
     * Unset the specified offset of the specified property.
     *
     * @param  mixed $offset
     * @return void
     */
    public function offsetUnset($offset)
    {
        unset($this->property[$offset]);
    }
}

$foo = new Foo([2, 4, 5]);
var_dump(isset($foo[0])); // bool(true)
var_dump($foo[0]);        // int(2)
unset($foo[0]);
var_dump(isset($foo[0])); // bool(false)
$foo[0] = 'foo';
var_dump($foo[0]);        // string(3) "foo"
$foo[] = 'bar';
$foo[] = 'baz';
$foo[] = 'qux';
var_dump($foo);           // object(Foo)#1 (1) { ["property":"Foo":private]=> array(6) { [1]=> int(4) [2]=> int(5) [0]=> string(3) "foo" [3]=> string(3) "bar" [4]=> string(3) "baz" [5]=> string(3) "qux" } }

```

