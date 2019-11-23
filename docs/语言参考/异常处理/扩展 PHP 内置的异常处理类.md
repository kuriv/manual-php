# 扩展 PHP 内置的异常处理类

用户可以用自定义的异常处理类来扩展 PHP 内置的异常处理类。如果使用自定义的类来扩展内置异常处理类，并且要重新定义构造函数的话，建议同时调用 `parent::__construct()` 来检查所有的变量是否已被赋值。当对象要输出字符串的时候，可以重载 `__toString()` 并自定义输出的样式。

```php
<?php

class NewException extends Exception
{
    /**
     * Override the parent constructor.
     *
     * @param string         $message
     * @param int            $code
     * @param Exception|null $previous
     */
    public function __construct(string $message, int $code, Exception $previous = null)
    {
        parent::__construct($message, $code, $previous);
    }
}

try {
    throw new NewException('foo', 1);
} catch (Exception $e) {
    var_dump($e->getMessage()); //string(3) "foo"
    var_dump($e->getCode());    // int(1)
}

```

