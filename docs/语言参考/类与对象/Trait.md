# Trait

PHP 实现了一种代码复用的方法，称为 Trait 。 Trait 是为类似 PHP 的单继承语言而准备的一种代码复用机制。 Trait 为了减少单继承语言的限制，使开发人员能够自由地在不同层次结构内独立的类中复用方法。 Trait 和类组合的语义定义了一种减少复杂性的方式，避免传统多继承和 Mixin 类相关典型问题。 Trait 和类相似，但仅仅旨在用细粒度和一致的方式来组合功能。无法通过 Trait 自身来实例化。它为传统继承增加了水平特性的组合，也就是说，应用的几个类之间不需要继承。

```php
<?php

trait Foo
{
    /**
     * Return a string.
     *
     * @param  void
     * @return string
     */
    public function method(): string
    {
        return 'foo';
    }
}

class Bar
{
    use Foo;
}

class Baz
{
    use Foo;
}

$bar = new Bar;
var_dump($bar->method()); // string(3) "foo"

$baz = new Baz;
var_dump($baz->method()); // string(3) "foo"

```

从基类继承的成员会被 Trait 插入的成员所覆盖。优先顺序是来自当前类的成员覆盖了 Trait 的方法，而 Trait 则覆盖了被继承的方法。

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
    public function method(): string
    {
        return 'foo';
    }
}

trait Bar
{
    /**
     * Return a string.
     *
     * @param  void
     * @return string
     */
    public function method(): string
    {
        return 'bar';
    }
}

class Baz extends Foo
{
    use Bar;
}

class Qux extends Foo
{
    use Bar;

    /**
     * Override the trait method.
     *
     * @param  void
     * @return string
     */
    public function method(): string
    {
        return 'baz';
    }
}

$baz = new Baz;
var_dump($baz->method()); // string(3) "bar"

$qux = new Qux;
var_dump($qux->method()); // string(3) "baz"

```

通过逗号分隔，在 `use` 声明列出多个 Trait ，可以都插入到一个类中。

```php
<?php

trait Foo
{
    /**
     * Return a string.
     *
     * @param  void
     * @return string
     */
    public function foo(): string
    {
        return 'foo';
    }
}

trait Bar
{
    /**
     * Return a string.
     *
     * @param  void
     * @return string
     */
    public function bar(): string
    {
        return 'bar';
    }
}

class Baz
{
    use Foo, Bar;
}

$baz = new Baz;
var_dump($baz->foo()); // string(3) "foo"
var_dump($baz->bar()); // string(3) "bar"

```

如果两个 Trait 都插入了一个同名的方法，如果没有明确解决冲突将会产生一个致命错误。为了解决多个 Trait 在同一个类中的命名冲突，需要使用 `insteadof` 操作符来明确指定使用冲突方法中的哪一个。以上方式仅允许排除掉其它方法， `as` 操作符可以 为某个方法引入别名。 注意， `as` 操作符不会对方法进行重命名，也不会影响其方法。

```php
<?php

trait Foo
{
    /**
     * Return a string.
     *
     * @param  void
     * @return string
     */
    public function method(): string
    {
        return 'foo';
    }
}

trait Bar
{
    /**
     * Return a string.
     *
     * @param  void
     * @return string
     */
    public function method(): string
    {
        return 'bar';
    }
}

class Baz
{
    use Foo, Bar
    {
        Foo::method insteadof Bar;
    }
}

class Qux
{
    use Foo, Bar
    {
        Bar::method insteadof Foo;
        Bar::method as test;
    }
}

$baz = new Baz;
var_dump($baz->method()); // string(3) "foo"

$qux = new Qux;
var_dump($qux->method()); // string(3) "bar"
var_dump($qux->test());   // string(3) "bar"

```

使用 `as` 语法还可以用来调整方法的访问控制。

```php
<?php

trait Foo
{
    /**
     * Return a string.
     *
     * @param  void
     * @return string
     */
    protected function method(): string
    {
        return 'foo';
    }
}

class Bar
{
    use Foo
    {
        Foo::method as public;
    }
}

class Baz
{
    use Foo
    {
        Foo::method as public test;
    }
}

$bar = new Bar;
var_dump($bar->method()); // string(3) "foo"

$baz = new Baz;
var_dump($baz->method()); // PHP Fatal error:  Uncaught Error: Call to protected method Baz::method() from context ''
var_dump($baz->test());   // string(3) "foo"

```

正如类能够使用 Trait 一样，其它 Trait 也能够使用 Trait 。在 Trait 定义时通过使用一个或多个 Trait ，能够组合其它 Trait 中的部分或全部成员。

```php
<?php

trait Foo
{
    /**
     * Return a string.
     *
     * @param  void
     * @return string
     */
    public function foo(): string
    {
        return 'foo';
    }
}

trait Bar
{
    /**
     * Return a string.
     *
     * @param  void
     * @return string
     */
    public function bar(): string
    {
        return 'bar';
    }
}

trait Baz
{
    use Foo, Bar;
}

class Qux
{
    use Baz;
}

$qux = new Qux;
var_dump($qux->foo()); // string(3) "foo"
var_dump($qux->bar()); // string(3) "bar"

```

为了对使用的类施加强制要求， Trait 支持抽象方法的使用。

```php
<?php

trait Foo
{
    /**
     * Just an abstract method.
     *
     * @param  void
     * @return string
     */
    abstract protected function method(): string;
}

class Bar
{
    use Foo;

    /**
     * Override the abstract method.
     *
     * @param  void
     * @return string
     */
    public function method(): string
    {
        return 'bar';
    }
}

$bar = new Bar;
var_dump($bar->method()); // string(3) "bar"

```

Trait 方法中的静态变量。

```php
<?php

trait Foo
{
    /**
     * Use static variables in method.
     *
     * @param  void
     * @return int
     */
    public static function method(): int
    {
        static $foo = 0;
        return $foo++;
    }
}

class Bar
{
    use Foo;
}

var_dump(Bar::method()); // int(0)
var_dump(Bar::method()); // int(1)
var_dump(Bar::method()); // int(2)

```

Trait 中的静态方法。

```php
<?php

trait Foo
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

class Bar
{
    use Foo;
}

var_dump(Bar::method()); // string(3) "foo"

```

Trait 中同样可以定义属性。 Trait 定义了一个属性后，类就不能定义同样名称的属性，否则会产生致命错误。 有种情况例外：属性是兼容的（同样的访问可见度、初始默认值）。 

```php
<?php

trait Foo
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
     * @var bool
     */
    public bool $bar = true;
}

class Bar
{
    use Foo;

    /**
     * Override the parent property.
     *
     * @var string
     */
    public string $foo = 'foo';

    /**
     * Try to override the parent property.
     *
     * @var bool
     */
    public bool $bar = false;
}

// PHP Fatal error:  Bar and Foo define the same property ($bar) in the composition of Bar. However, the definition differs and is considered incompatible.

```

