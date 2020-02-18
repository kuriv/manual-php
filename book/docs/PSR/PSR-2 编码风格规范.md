# PSR-2 编码风格规范

* [通则](#通则)
  * [基本编码准则](#基本编码准则)
  * [文件](#文件)
  * [行](#行)
  * [缩进](#缩进)
  * [关键字以及 true / false / null](#关键字以及-true--false--null)
* [namespace 及 use 声明](#namespace-及-use-声明)
* [类、属性和方法](#类、属性和方法)
  * [扩展与继承](#扩展与继承)
  * [属性](#属性)
  * [方法](#方法)
  * [方法的参数](#方法的参数)
  * [abstract 和 final 和 static](#abstract-和-final-和-static)
  * [方法及函数调用](#方法及函数调用)
* [控制结构](#控制结构)
  * [if 和 elseif 和 else](#if-和-elseif-和-else)
  * [switch 和 case](#switch-和-case)
  * [while 和 do-while](#while-和-do-while)
  * [for](#for)
  * [foreach](#foreach)
  * [try 和 catch](#try-和-catch)
* [闭包](#闭包)

## 通则

### 基本编码准则

> 代码 **必须** 符合 PSR-1 中的所有规范。

### 文件

> 所有 PHP 文件 **必须** 使用 Unix 的 `LF` 作为行的结束符。
>
> 所有 PHP 文件 **必须** 以一个空白行作为结束。
>
> 纯 PHP 代码文件 **必须** 省略最后的 `?>` 结束标签。

### 行

> 行的长度 **一定不可** 有硬性的约束。
>
> 软性的长度约束 **必须** 要限制在 120 个字符以内，若超过此长度，带代码规范检查的编辑器 **必须** 要发出警告，不过 **一定不可** 发出错误提示。
>
> 每行 **不该** 多于 80 个字符，大于 80 字符的行 **应该** 折成多行。
>
> 非空行后 **一定不可** 有多余的空格符。
>
> 空行 **可以** 使得阅读代码更加方便以及有助于代码的分块。
>
> 每行 **一定不可** 存在多于一条语句。

### 缩进

> 代码 **必须** 使用 4 个空格符的缩进， **一定不可** 用 Tab 键。

### 关键字以及 true / false / null

> PHP 所有关键字 **必须** 全部小写。
>
> 常量 `true` 、 `false` 和 `null` 也 **必须** 全部小写。

## namespace 及 use 声明

> `namespace` 声明后 **必须** 插入一个空白行。
>
> 所有 `use` **必须** 在 `namespace` 后声明。
>
> 每条 `use` 声明语句 **必须** 只有一个 `use` 关键词。
>
> `use` 声明语句块后 **必须** 要有一个空白行。

```php
<?php

namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

```

## 类、属性和方法

### 扩展与继承

> 关键词 `extends` 和 `implements` **必须** 写在类名称的同一行。
>
> 类的开始花括号 **必须** 独占一行，结束花括号也 **必须** 在类主体后独占一行。

```php
<?php

namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClassName implements \ArrayAccess, \Countable
{
    //
}

```

> `implements` 的继承列表也 **可以** 分成多行，这样的话，每个继承接口名称都 **必须** 分开独立成行，包括第一个。

```php
<?php

namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClassName implements
    \ArrayAccess,
    \Countable,
    \Serializable
{
    //
}

```

### 属性

> 每个属性都 **必须** 添加访问修饰符。
>
> **一定不可** 使用关键字 `var` 声明一个属性。
>
> 每条语句 **一定不可** 定义超过一个属性。
>
> **不该** 使用下划线作为前缀，来区分属性是 `protected` 或 `private` 。

```php
<?php

namespace Vendor\Package;

class ClassName
{
    /**
     * Just a test property.
     *
     * @var string|null
     */
    public ?string $propertyName = null;
}

```

### 方法

> 所有方法都 **必须** 添加访问修饰符。
>
> **不该** 使用下划线作为前缀，来区分方法是 `protected` 或 `private` 。
>
> 方法名称后 **一定不可** 有空格符，其开始花括号 **必须** 独占一行，结束花括号也 **必须** 在方法主体后单独成一行。参数左括号后和右括号前 **一定不可** 有空格。

```php
<?php

namespace Vendor\Package;

class ClassName
{
    /**
     * Just a test method.
     *
     * @param  void
     * @return void
     */
    public function methodName()
    {
        //
    }
}

```

### 方法的参数

> 参数列表中，每个逗号后面 **必须** 要有一个空格，而逗号前面 **一定不可** 有空格。
>
> 有默认值的参数， **必须** 放到参数列表的末尾。

```php
<?php

namespace Vendor\Package;

class ClassName
{
    /**
     * Just a test method.
     *
     * @param  int    $arg1
     * @param  string $arg2
     * @param  array  $arg3
     * @return void
     */
    public function methodName(int $arg1, string $arg2, array $arg3 = [])
    {
        //
    }
}

```

> 参数列表 **可以** 分列成多行，这样，包括第一个参数在内的每个参数都 **必须** 单独成行。
>
> 拆分成多行的参数列表后，结束括号以及方法开始花括号 **必须** 写在同一行，中间用一个空格分隔。

```php
<?php

namespace Vendor\Package;

class ClassName
{
    /**
     * Just a test method.
     *
     * @param  int    $arg1
     * @param  string $arg2
     * @param  array  $arg3
     * @return void
     */
    public function methodName(
        int $arg1,
        string $arg2,
        array $arg3 = []
    ) {
        //
    }
}

```

### abstract 和 final 和 static

> 需要添加 `abstract` 或 `final` 声明时， **必须** 写在访问修饰符前，而 `static` 则 **必须** 写在其后。

```php
<?php

namespace Vendor\Package;

abstract class ClassName
{
    /**
     * Just a test property.
     *
     * @var string|null
     */
    protected static ?string $propertyName = null;

    /**
     * Just an abstract method.
     *
     * @param  void
     * @return void
     */
    abstract protected function methodName();

    /**
     * Just a test method.
     *
     * @param  void
     * @return void
     */
    final public static function anotherMethodName()
    {
        //
    }
}

```

### 方法及函数调用

> 方法及函数调用时，方法名或函数名与参数左括号之间 **一定不可** 有空格，参数右括号前也 **一定不可** 有空格。每个参数前 **一定不可** 有空格，但其后 **必须** 有一个空格。

```php
<?php

foo();
$foo->bar($arg1);
Foo::bar($arg2, $arg3);

```

> 参数 **可以** 分列成多行，此时包括第一个参数在内的每个参数都 **必须** 单独成行。

```php
<?php

$foo->bar(
    $longArgument,
    $longerArgument,
    $muchLongerArgument
);

```

## 控制结构

### if 和 elseif 和 else

```php
<?php

if ($expr1) {
    //
} elseif ($expr2) {
    //
} else {
    //
}

```

### switch 和 case

> `case` 语句 **必须** 相对 `switch` 进行一次缩进，而 `break` 语句以及 `case` 内的其它语句都 **必须** 相对 `case` 进行一次缩进。
>
> 如果存在非空的 `case` 语句，主体里 **必须** 有类似 `// no break` 的注释。

```php
<?php

switch ($expr) {
    case 0:
        echo 0;
        break;
    case 1:
        echo 1;
        // no break
    case 2:
    case 3:
    case 4:
        echo 4;
        return;
    default:
        echo 'default';
        break;
}

```

### while 和 do-while

```php
<?php

while ($expr) {
    //
}

```

```php
<?php

do {
    //
} while ($expr);

```

### for

```php
<?php

for ($i = 0; $i < 10; $i++) {
    //
}

```

### foreach

```php
<?php

foreach ($iterable as $key => $value) {
    //
}

```

### try 和 catch

```php
<?php

try {
    //
} catch (FirstExceptionType $e) {
    //
} catch (OtherExceptionType $e) {
    //
}

```

## 闭包

> 闭包声明时，关键词 `function` 后以及关键词 `use` 的前后都 **必须** 要有一个空格。
>
> 开始花括号 **必须** 写在声明的同一行，结束花括号 **必须** 紧跟主体结束的下一行。
>
> 参数列表和变量列表的左括号后以及右括号前， **一定不可** 有空格。
>
> 参数和变量列表中，逗号前 **一定不可** 有空格，而逗号后 **必须** 要有空格。
>
> 闭包中有默认值的参数 **必须** 放到列表的后面。

```php
<?php

/**
 * Just a test function.
 *
 * @param  int    $arg1
 * @param  string $arg2
 * @return void
 */
$closureWithArgs = function (int $arg1, string $arg2) {
};

/**
 * Just a test function.
 *
 * @param  int    $arg1
 * @param  string $arg2
 * @return void
 */
$closureWithArgsAndVars = function (int $arg1, string $arg2) use ($var1, $var2) {
};

```

> 参数列表以及变量列表 **可以** 分成多行，这样，包括第一个在内的每个参数或变量都 **必须** 单独成行，而列表的右括号与闭包的开始花括号 **必须** 放在同一行。

```php
<?php

/**
 * Just a test function.
 *
 * @param  int    $longArgument
 * @param  string $longerArgument
 * @param  array  $muchLongerArgument
 * @return void
 */
$longArgs_noVars = function (
    int $longArgument,
    string $longerArgument,
    array $muchLongerArgument
) {
};

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
$noArgs_longVars = function () use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
};

/**
 * Just a test function.
 *
 * @param  int    $longArgument
 * @param  string $longerArgument
 * @param  array  $muchLongerArgument
 * @return void
 */
$longArgs_longVars = function (
    int $longArgument,
    string $longerArgument,
    array $muchLongerArgument
) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
};

/**
 * Just a test function.
 *
 * @param  int    $longArgument
 * @param  string $longerArgument
 * @param  array  $muchLongerArgument
 * @return void
 */
$longArgs_shortVars = function (
    int $longArgument,
    string $longerArgument,
    array $muchLongerArgument
) use ($var) {
};

/**
 * Just a test function.
 *
 * @param  int  $arg
 * @return void
 */
$shortArgs_longVars = function (int $arg) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
};

```

> 注意，闭包被直接用作函数或方法调用的参数时，以上规则仍然适用。

```php
<?php

$foo->bar(
    $arg1,
    function ($arg2) use ($var) {
        //
    },
    $arg3
);

```

