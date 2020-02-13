# elseif

和 `else` 一样， `elseif` 延伸了 `if` 语句，可以在原来的 `if` 表达式值为 `false` 时执行不同语句。但是和 `else` 不一样的是，它仅在 `elseif` 的条件表达式值为 `true` 时执行语句。在同一个 `if` 语句中可以有多个 `elseif` 部分，其中第一个表达式值为 `true` （如果有的话）的 `elseif` 部分将会执行。 `elseif` 的语句仅在之前的 `if` 和所有之前 `elseif` 的表达式值为 `false` ，并且当前的 `elseif` 表达式值为 `true` 时执行。

```php
<?php

$baz = 'baz';
if (isset($foo)) {
    //
} elseif (isset($bar)) {
    //
} elseif (isset($baz)) {
    //
}

```

