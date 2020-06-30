# PHP 标准库

* 数据结构
  * SplDoublyLinkedList
  * SplStack
  * SplQueue
  * SplHeap
  * SplMaxHeap
  * SplMinHeap
  * SplPriorityQueue
  * SplFixedArray
  * SplObjectStorage
* 迭代器
  * AppendIterator
  * ArrayIterator
  * CachingIterator
  * CallbackFilterIterator
  * DirectoryIterator
  * EmptyIterator
  * FilesystemIterator
  * FilterIterator
  * GlobIterator
  * InfiniteIterator
  * IteratorIterator
  * LimitIterator
  * MultipleIterator
  * NoRewindIterator
  * ParentIterator
  * RecursiveArrayIterator
  * RecursiveCachingIterator
  * RecursiveCallbackFilterIterator
  * RecursiveDirectoryIterator
  * RecursiveFilterIterator
  * RecursiveIteratorIterator
  * RecursiveRegexIterator
  * RecursiveTreeIterator
  * RegexIterator
* 接口
  * Countable
  * OuterIterator
  * RecursiveIterator
  * SeekableIterator
* 异常
  * BadFunctionCallException
  * BadMethodCallException
  * DomainException
  * InvalidArgumentException
  * LengthException
  * LogicException
  * OutOfBoundsException
  * OutOfRangeException
  * OverflowException
  * RangeException
  * RuntimeException
  * UnderflowException
  * UnexpectedValueException
* 文件处理
  * SplFileInfo
  * SplFileObject
  * SplTempFileObject
* 各种类及接口
  * ArrayObject
  * SplObserver
  * SplSubject
* [SPL](#spl)
  * [class_implements - 返回指定的类实现的所有接口](#classimplements)
  * [class_parents - 返回指定类的父类](#classparents)
  * [class_uses - 返回指定类使用的 Trait](#classuses)
  * [iterator_apply - 为迭代器中每个元素调用一个用户自定义函数](#iteratorapply)
  * [iterator_count - 计算迭代器中元素的个数](#iteratorcount)
  * [iterator_to_array - 将迭代器中的元素拷贝到数组](#iteratortoarray)
  * [spl_autoload_call - 尝试调用所有已注册的 __autoload() 函数来装载请求类](#splautoloadcall)
  * [spl_autoload_extensions - 注册并返回 spl_autoload 函数使用的默认文件扩展名](#splautoloadextensions)
  * [spl_autoload_functions - 返回所有已注册的 __autoload() 函数](#splautoloadfunctions)
  * [spl_autoload_register - 注册给定的函数作为 __autoload 的实现](#splautoloadregister)
  * [spl_autoload_unregister - 注销已注册的 __autoload() 函数](#splautoloadunregister)
  * [spl_autoload - __autoload() 函数的默认实现](#splautoload)
  * [spl_classes - 返回所有可用的 SPL 类](#splclasses)
  * [spl_object_hash - 返回指定对象的 Hash ID](#splobjecthash)
  * [spl_object_id - 返回指定对象的整数对象句柄](#splobjectid)

## SPL

### class_implements

```php
<?php

interface Foo
{
    //
}

class Bar implements Foo
{
    //
}

var_dump(class_implements('Foo'));   // array(0) { }
var_dump(class_implements('Bar'));   // array(1) { ["Foo"]=> string(3) "Foo" }
var_dump(class_implements(new Bar)); // array(1) { ["Foo"]=> string(3) "Foo" }

```

### class_parents

```php
<?php

class Foo
{
    //
}

class Bar extends Foo
{
    //
}

var_dump(class_parents('Foo'));   // array(0) { }
var_dump(class_parents('Bar'));   // array(1) { ["Foo"]=> string(3) "Foo" }
var_dump(class_parents(new Bar)); // array(1) { ["Foo"]=> string(3) "Foo" }

```

### class_uses

```php
<?php

trait Foo
{
    //
}

class Bar
{
    use Foo;
}

var_dump(class_uses('Foo'));   // array(0) { }
var_dump(class_uses('Bar'));   // array(1) { ["Foo"]=> string(3) "Foo" }
var_dump(class_uses(new Bar)); // array(1) { ["Foo"]=> string(3) "Foo" }

```

### iterator_apply

```php
<?php

/**
 * Just a test function.
 *
 * @param  Iterator $iterator
 * @return bool
 */
function foo(Iterator $iterator): bool
{
    var_dump($iterator->current());
    return true;
}

$iterator = new ArrayIterator([2, 3, 5]);
iterator_apply($iterator, 'foo', [$iterator]);
// int(2)
// int(3)
// int(5)

```

### iterator_count

```php
<?php

$iterator = new ArrayIterator();
var_dump(iterator_count($iterator)); // int(0)

$iterator = new ArrayIterator([2, 3, 5, 'foo', 'bar']);
var_dump(iterator_count($iterator)); // int(5)

```

### iterator_to_array

```php
<?php

$iterator = new ArrayIterator(['foo' => 'foo', 'bar' => 'bar']);
var_dump(iterator_to_array($iterator));        // array(2) { ["foo"]=> string(3) "foo" ["bar"]=> string(3) "bar" }
var_dump(iterator_to_array($iterator, false)); // array(2) { [0]=> string(3) "foo" [1]=> string(3) "bar" }

```

### spl_autoload_call

```php
<?php

spl_autoload_call('Foo');
var_dump(new Foo); // object(Foo)#1 (0) { }

spl_autoload_call('Bar');
var_dump(new Bar); // object(Bar)#1 (0) { }

```

### spl_autoload_extensions

```php
<?php

var_dump(spl_autoload_extensions());            // string(9) ".inc,.php"
var_dump(spl_autoload_extensions('.inc,.php')); // string(9) ".inc,.php"

```

### spl_autoload_functions

```php
<?php

var_dump(spl_autoload_functions());

```

### spl_autoload_register

```php
<?php

/**
 * Include the specified file.
 *
 * @param  string $class
 * @return void
 */
function foo(string $class)
{
    include $class . '.php';
}

$foo = spl_autoload_register('foo');
$bar = spl_autoload_register(function (string $class) {
    include $class . '.php';
});
var_dump(new Foo); // object(Foo)#2 (0) { }
var_dump(new Bar); // object(Bar)#2 (0) { }

```

上例中的 `Foo.php` 文件内容：

```php
<?php

class Foo
{
    //
}

```

上例中的 `Bar.php` 文件内容：

```php
<?php

class Bar
{
    //
}

```

### spl_autoload_unregister

```php
<?php

/**
 * Include the specified file.
 *
 * @param  string $class
 * @return void
 */
function foo(string $class)
{
    include $class . '.php';
}

$foo = spl_autoload_register('foo');
$bar = spl_autoload_register(function (string $class) {
    include $class . '.php';
});

$functions = spl_autoload_functions();
foreach ($functions as $function) {
    var_dump(spl_autoload_unregister($function));
}
// bool(true)
// bool(true)

```

### spl_autoload

```php
<?php

spl_autoload_register();
var_dump(new Foo); // object(Foo)#1 (0) { }
var_dump(new Bar); // object(Bar)#1 (0) { }

```

上例中的 `Foo.php` 文件内容：

```php
<?php

class Foo
{
    //
}

```

上例中的 `Bar.php` 文件内容：

```php
<?php

class Bar
{
    //
}

```

### spl_classes

```php
<?php

var_dump(spl_classes());

```

### spl_object_hash

```php
<?php

class Foo
{
    //
}

var_dump(spl_object_hash(new Foo));

```

### spl_object_id

```php
<?php

class Foo
{
    //
}

var_dump(spl_object_id(new Foo));

```