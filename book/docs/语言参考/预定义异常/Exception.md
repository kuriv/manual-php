# Exception

`Exception` 是所有异常的基类。

```php
<?php

try {
    throw new Exception('foo', 1);
} catch (Exception $e) {
    var_dump(new Exception('bar', 2, $e));
}

```

返回异常消息内容。

```php
<?php

try {
    throw new Exception('foo');
} catch (Exception $e) {
    var_dump($e->getMessage()); // string(3) "foo"
}

```

返回异常链中的前一个异常。

```php
<?php

try {
    throw new Exception('foo', 1);
} catch (Exception $e) {
    var_dump((new Exception('bar', 2, $e))->getPrevious());
}

```

返回异常代码。

```php
<?php

try {
    throw new Exception('foo', 1);
} catch (Exception $e) {
    var_dump($e->getCode()); // int(1)
}

```

获取创建异常的程序文件名称。

```php
<?php

try {
    throw new Exception();
} catch (Exception $e) {
    var_dump($e->getFile());
}

```

返回发生异常的代码在文件中的行号。

```php
<?php

try {
    throw new Exception();
} catch (Exception $e) {
    var_dump($e->getLine()); // int(6)
}

```

以数组类型返回异常追踪信息。

```php
<?php

/**
 * Throwing an exception.
 *
 * @param  void
 * @return void
 */
function foo()
{
    throw new Exception();
}

try {
    foo();
} catch (Exception $e) {
    var_dump($e->getTrace());
}

```

以字符串类型返回异常追踪信息。

```php
<?php

/**
 * Throwing an exception.
 *
 * @param  void
 * @return void
 */
function foo()
{
    throw new Exception();
}

try {
    foo();
} catch (Exception $e) {
    var_dump($e->getTraceAsString());
}

```

返回转换为字符串类型的异常。

```php
<?php

/**
 * Throwing an exception.
 *
 * @param  void
 * @return void
 */
function foo()
{
    throw new Exception();
}

try {
    foo();
} catch (Exception $e) {
    echo $e;
}

```

尝试克隆异常，这将导致一个致命错误。

```php
<?php

$foo = new Exception();
$bar = clone $foo;
// PHP Fatal error:  Uncaught Error: Trying to clone an uncloneable object of class Exception.

```

