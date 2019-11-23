# Final 关键字

如果一个类被声明为 `final` ，则不能被继承。

```php
<?php

final class Foo
{
}

class Bar extends Foo
{
}

// PHP Fatal error:  Class Bar may not inherit from final class (Foo).

```

如果父类中的方法被声明为 `final` ，则子类无法覆盖该方法。

```php
<?php

class Foo
{
    /**
     * Just a test method.
     *
     * @param  void
     * @return void
     */
    final public function method()
    {
    }
}

class Bar extends Foo
{
    /**
     * Try to override the parent method.
     *
     * @param  void
     * @return void
     */
    public function method()
    {
    }
}

// PHP Fatal error:  Cannot override final method Foo::method().

```

