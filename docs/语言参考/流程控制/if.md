# if

`if` 结构是很多语言包括 PHP 在内最重要的特性之一，它允许按照条件执行代码片段。

```php
<?php

$foo = 'foo';
if (isset($foo)) {
    //
}

```

`if` 语句可以无限层地嵌套在其它 `if` 语句中，这给程序的不同部分的条件执行提供了充分的弹性。

```php
<?php

$foo = 'foo';
if (isset($foo)) {
    if ($foo == 'foo') {
        //
    }
}

```

