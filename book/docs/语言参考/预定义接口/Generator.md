# Generator

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
    for ($i = 0; $i < 10; $i++) {
        yield $i;
    }
}

/**
 * Receive a value.
 *
 * @param  void
 * @return void
 */
function bar()
{
    while (true) {
        var_dump(yield);
    }
}

/**
 * Yielding test values and Receive a value.
 *
 * @param  void
 * @return void
 */
function baz()
{
    $i = 0;
    while (true) {
        var_dump(yield $i++);
    }
}

$foo = foo();
foreach ($foo as $value) {
    var_dump($value);
}
// int(0)
// int(1)
// int(2)
// int(3)
// int(4)
// int(5)
// int(6)
// int(7)
// int(8)
// int(9)

$bar = bar();
$bar->send('bar');         // string(3) "bar"

$baz = baz();
$baz->rewind();
$baz->send('baz');         // string(3) "baz"
var_dump($baz->current()); // int(1)
var_dump($baz->key());     // int(1)
$baz->next();              // NULL
var_dump($baz->current()); // int(2)
var_dump($baz->valid());   // bool(true)

```

