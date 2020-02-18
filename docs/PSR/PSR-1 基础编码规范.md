# PSR-1 基础编码规范

* [文件](#文件)
  * [PHP 标签](#php-标签)
  * [字符编码](#字符编码)
  * [副作用](#副作用)
* [命名空间和类](#命名空间和类)
* [类的常量、属性和方法](#类的常量、属性和方法)
  * [常量](#常量)
  * [属性](#属性)
  * [方法](#方法)

## 文件

### PHP 标签

> PHP 代码 **必须** 使用 `<?php ?>` 长标签或 `<?= ?>` 短标签， **一定不可** 使用其它自定义标签。

### 字符编码

> PHP 代码 **必须** 使用 `不带 BOM 的 UTF-8` 编码。

### 副作用

> 一份 PHP 文件中 **应该** 要不就只定义新的声明，如类、函数或常量等不产生副作用的操作，要不就只书写会产生副作用的逻辑操作，但 **不该** 同时具有两者。

下面是一个包含函数声明以及产生副作用的例子：

```php
<?php

//
ini_set('display_errors', '1');

//
require __DIR__ . '/example.php';

//
echo '<html>';

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    //
}

```

下面是一个只包含函数声明不产生副作用的例子：

```php
<?php

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    //
}

if (!function_exists('bar')) {
    /**
     * Just a test function.
     *
     * @param  void
     * @return void
     */
    function bar()
    {
        //
    }
}

```

## 命名空间和类

> 命名空间以及类的命名 **必须** 遵循 PSR-4 。
>
> 根据规范，每个类都独立为一个文件，且命名空间至少有一个层次：顶级的组织名称。
>
> 类的命名 **必须** 遵循 `StudlyCaps` 大写开头的驼峰命名规范。

```php
<?php

namespace Vendor\Package;

class StudlyCaps
{
    //
}

```

## 类的常量、属性和方法

### 常量

> 类的常量中所有字母都 **必须** 大写，词间以下划线分隔。

```php
<?php

namespace Vendor\Package;

class StudlyCaps
{
    /**
     * Just a test constant.
     *
     * @var string
     */
    const VERSION = '1.0';

    /**
     * Just a test constant.
     *
     * @var string
     */
    const DATE_APPROVED = '2019-01-01';
}

```

### 属性

> 类的属性命名 **可以** 遵循：大写开头的驼峰式 `$StudlyCaps` 、小写开头的驼峰式 `$camelCase` 、下划线分隔式 `$under_score` 。

### 方法

> 类的方法名称 **必须** 符合 `camelCase()` 式的小写开头驼峰命名规范。

