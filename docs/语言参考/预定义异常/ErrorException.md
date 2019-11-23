# ErrorException

`Exception` 异常构造函数。

```php
<?php

try {
    throw new ErrorException('foo', 1);
} catch (Exception $e) {
    var_dump(new ErrorException('bar', 2, 2, __DIR__ . '/example.php', 10, $e));
}

```

返回异常的严重程度。

```php
<?php

try {
    throw new ErrorException('foo', 1, 1);
} catch (Exception $e) {
    var_dump($e->getSeverity()); // int(1)
}

```

