# PSR-12 编码规范扩充

* [总则](#总则)
  * [基本编码准则](#基本编码准则)
  * [文件](#文件)
  * [行](#行)
  * [缩进](#缩进)
  * [关键字和类型](#关键字和类型)
* [声明和命名空间以及导入](#声明和命名空间以及导入)
* [类和属性和方法](#类和属性和方法)
  * [继承和实现](#继承和实现)
  * [使用 Trait](#使用-trait)
  * [属性和常量](#属性和常量)
  * [方法和函数](#方法和函数)
  * [方法和函数参数](#方法和函数参数)
  * [abstract 和 final 和 static](#abstract-和-final-和-static)
  * [方法和函数的调用](#方法和函数的调用)
* [流程控制](#流程控制)
  * [if 和 elseif 和 else](#if-和-elseif-和-else)
  * [switch 和 case](#switch-和-case)
  * [while 和 do-while](#while-和-do-while)
  * [for](#for)
  * [foreach](#foreach)
  * [try 和 catch 和 finally](#try-和-catch-和-finally)
* [运算符](#运算符)
  * [一元运算符](#一元运算符)
  * [二元运算符](#二元运算符)
  * [三元运算符](#三元运算符)
* [闭包](#闭包)
* [匿名类](#匿名类)

## 总则

### 基本编码准则

> 代码 **必须** 遵循 PSR-1 中的所有规范。
>
> PSR-1 中的术语 `StudlyCaps`  **必须** 解释为 `PascalCase` ，其中每个单词的首字母大写，包括首字母。

### 文件

> 所有 PHP 文件 **必须** 使用 Unix 的 `LF` 作为行的结束符。
>
> 所有 PHP 文件 **必须** 以非空行结尾，并且使用 Unix 的 `LF` 结尾。
>
> 在仅包含 PHP 代码的文件中， **必须** 省略结尾的 `?>` 结束标签。

### 行

> 行的长度 **一定不可** 有硬性的约束。
>
> 行的长度的软性约束 **必须** 要限制在 120 个字符以内。
>
> 每行 **不该** 多于 80 个字符，大于 80 字符的行 **应该** 折成多行。
>
> 行尾 **一定不可** 有多余的空格符。
>
> **可以** 添加空行以提高可读性并指示相关的代码块，除非明确禁止。
>
> 每行 **一定不可** 存在多于一条语句。

### 缩进

> 代码 **必须** 使用 4 个空格符的缩进， **一定不可** 用 Tab 键。

### 关键字和类型

> PHP 所有关键字 **必须** 全部小写。
>
> PHP 未来版本中新添加的所有关键字和类型也都 **必须** 使用小写。
>
> 类型关键字 **必须** 使用缩写，使用 `bool` 而不是 `boolean` ，使用 `int` 而不是 `integer` 等等。

## 声明和命名空间以及导入

> 一个 PHP 文件的头部 **可能** 会包含多个块，如果包含多个块，则每个块都 **必须** 用空白行和其他块分隔，并且同样的块内 **不能** 包含空白行。
>
> 所有的块都 **必须** 按照下面的顺序排列，如果不存在该块则忽略。
>
> * PHP 文件开始标签 `<?php`
> * 文件级文档块
> * 一个或多个声明语句
> * 命名空间声明语句
> * 一个或多个基于类的 `use` 声明语句
> * 一个或多个基于方法的 `use` 声明语句
> * 一个或多个基于常量的 `use` 声明语句
> * 其余代码

```php
<?php

declare(strict_types=1);

namespace Vendor\Package;

use Vendor\Package\ClassA as A;
use Vendor\Package\ClassB;
use Vendor\Package\ClassC as C;

use function Vendor\Package\functionA;
use function Vendor\Package\functionB;
use function Vendor\Package\functionC;

use const Vendor\Package\CONSTANT_A;
use const Vendor\Package\CONSTANT_B;
use const Vendor\Package\CONSTANT_C;

class ClassName
{
    //
}

```

> 当希望在 PHP 代码外部包含标记的文件中声明严格类型时打开和关闭标签，声明 **必须** 写在文件的第一行，并且包含在第一个开始的 PHP 标签中。

```php
<?php declare(strict_types=1); ?>
<!DOCTYPE html>
<html>
    <head>
    </head>
    <body>
        <?php
            //
        ?>
    </body>
</html>

```

> 声明语句中 **不能** 包含空格。

```php
<?php

declare(ticks=1);

```

## 类和属性和方法

> 任何注释和语句 **一定不可** 跟在其右花括号后的同一行。
>
> 当实例化一个类时，后面的圆括号 **必须** 写出来，即使没有参数传进其构造函数。

```php
<?php

new Foo();

```

### 继承和实现

> 关键字 `extends` 和 `implements` **必须** 写在类名称的同一行。
>
> 类的左花括号 **必须** 另起一行，右花括号 **必须** 跟在类主体的下一行。
>
> 类的左花括号 **必须** 独自成行，且 **一定不可** 在其上一行或下一行存在空行。
>
> 类的右花括号 **必须** 独自成行，且 **一定不可** 在其上一行存在空行。

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

> `implements` 的列表 **可以** 分成多行，如果分成多行的话，第一个接口 **必须** 写在下一行，并且每行 **必须** 只写一个接口。

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

### 使用 Trait

> 在类里面使用 Trait **必须** 在左花括号的下一行声明。

```php
<?php

namespace Vendor\Package;

use Vendor\Package\FirstTrait;

class ClassName
{
    use FirstTrait;
}

```

> 每个导入到类中的 Trait **必须** 包含一个声明，且每个包含声明 **必须** 有其导入语句。

```php
<?php

namespace Vendor\Package;

use Vendor\Package\FirstTrait;
use Vendor\Package\SecondTrait;
use Vendor\Package\ThirdTrait;

class ClassName
{
    use FirstTrait;
    use SecondTrait;
    use ThirdTrait;
}

```

> 在类文件中，如果在使用 Trait 之后没有其他内容了，类名右大括号 **必须** 另起一行。

```php
<?php

namespace Vendor\Package;

use Vendor\Package\FirstTrait;

class ClassName
{
    use FirstTrait;
}

```

> 如有其他内容，两者之间 **必须** 空一行。

```php
<?php

namespace Vendor\Package;

use Vendor\Package\FirstTrait;

class ClassName
{
    use FirstTrait;

    /**
     * Just a test property.
     *
     * @var string
     */
    private string $propertyName = 'foo';
}

```

> 当使用 `insteadof` 和 `as` 运算符时，它们 **必须** 如下所示使用，注意缩进、间距和另起一行。

```php
<?php

namespace Vendor\Package;

class Talker
{
    use A, B, C {
        B::smallTalk insteadof A;
        A::bigTalk insteadof C;
        C::mediumTalk as FooBar;
    }
}

```

### 属性和常量

> 每个属性都 **必须** 添加访问修饰符。
>
> 如果你的 PHP 版本支持常量可见性，那么所有常量 **必须** 声明可见性。
>
> **一定不可** 使用关键字 `var` 声明一个属性。
>
> 每条语句 **一定不可** 定义超过一个属性。
>
> **一定不可** 使用下划线作为前缀，来区分属性是 `protected` 或 `private` 。
>
> 类型声明和属性名之间 **必须** 有一个空格。

```php
<?php

namespace Vendor\Package;

class ClassName
{
    /**
     * Just a test property.
     *
     * @var integer
     */
    public int $propertyName = 2;

    /**
     * Just a test property.
     *
     * @var string
     */
    public static string $anotherPropertyName = 'bar';
}

```

### 方法和函数

> 所有方法都 **必须** 添加访问修饰符。
>
> **一定不可** 使用下划线作为前缀，来区分方法是 `protected` 或 `private` 。
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

```php
<?php

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function functionName()
{
    //
}

```

### 方法和函数参数

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

> 参数列表 **可以** 分成多行，这样，包括第一个参数在内的每个参数都 **必须** 单独成行。
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

> 当你定义一个返回值类型声明时，冒号后面的类型声明 **必须** 用空格符隔开。
>
> 冒号和声明 **必须** 在同一行，且跟参数列表后的结束括号之间没有空格。

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
     * @return string
     */
    public function methodName(int $arg1, string $arg2): string
    {
        return 'foo';
    }

    /**
     * Just a test method.
     *
     * @param  int    $arg1
     * @param  string $arg2
     * @param  array  $arg3
     * @return string
     */
    public function anotherMethodName(
        int $arg1,
        string $arg2,
        array $arg3 = []
    ): string {
        return 'foo';
    }
}

```

> 在可空类型声明中，问号和类型声明之间 **不能** 有空格。

```php
<?php

namespace Vendor\Package;

class ClassName
{
    /**
     * Just a test method.
     *
     * @param  int|null    $arg1
     * @param  string|null $arg2
     * @return string|null
     */
    public function methodName(?int $arg1, ?string $arg2): ?string
    {
        return 'foo';
    }
}

```

> 当在参数前使用引用运算符时，引用运算符之后 **不能** 有空格。
>
> 可变参数运算符和参数名称之间 **不能** 有空格。

```php
<?php

namespace Vendor\Package;

class ClassName
{
    /**
     * Just a test method.
     *
     * @param  int    &$arg1
     * @param  string &$arg2
     * @param  int    $arg3
     * @return void
     */
    public function methodName(int &$arg1, string &$arg2, int ...$arg3)
    {
        //
    }
}

```

> 当同时使用引用运算符和可变参数运算符时，它们之间 **不能** 有任何空格。

```php
<?php

namespace Vendor\Package;

class ClassName
{
    /**
     * Just a test method.
     *
     * @param  int    &$arg1
     * @param  int    $arg2
     * @return void
     */
    public function methodName(int &$arg1, int &...$arg2)
    {
        //
    }
}

```

### abstract 和 final 和 static

> 需要添加 `abstract` 或 `final` 声明时， `abstract` **必须** 写在访问修饰符之前，而 `static` 则 **必须** 写在访问修饰符之后。

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
    protected static ?string $propertyName;

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

### 方法和函数的调用

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

## 流程控制

> 流程控制关键字之后 **必须** 要有一个空格。
>
> 左括号后面 **不能** 有空格，右括号前面 **不能** 有空格。
>
> 右括号与左大括号之间 **必须** 要有一个空格。
>
> 流程主体 **必须** 要缩进一次。
>
> 流程主体 **必须** 在左大括号之后另起一行。
>
> 右大括号 **必须** 在流程主体之后另起一行。
>
> 每个流程控制主体 **必须** 以封闭的括号结束，这将标准化流程结构，同时减少由于流程中添加新的内容而引入错误的可能性。

### if 和 elseif 和 else

> 关键字 `elseif` **应该** 替换 `else if` ，这样流程控制关键字看起来像一个词。

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

> 括号中的表达式 **可能** 会被分开为多行，每一行至少缩进一次。如果这样做，第一个条件 **必须** 在新的一行。右括号和左大括号 **必须** 在同一行，而且中间有一个空格。条件中间的逻辑运算符 **必须** 在每一行的开头或者结尾，而不是混在一起。

```php
<?php

if (
    $expr1
    && $expr2
) {
    //
} elseif (
    $expr3
    && $expr4
) {
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

> 括号中的表达式 **可能** 会被分开多行，每一行至少要缩进一次。如果这样做，第一个条件 **必须** 在新的一行。右括号和左大括号 **必须** 在同一行，而且中间有一个空格。条件中间的逻辑运算符 **必须** 在每一行的开头或者结尾，而不是混在一起。

```php
<?php

switch (
    $expr1
    && $expr2
) {
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

do {
    //
} while ($expr);

```

> 括号中的表达式 **可能** 会被分开多行，每一行至少要缩进一次。如果这样做，第一个条件 **必须** 在新的一行。右括号和左大括号 **必须** 在同一行，而且中间有一个空格。条件中间的逻辑运算符 **必须** 在每一行的开头或者结尾，而不是混在一起。

```php
<?php

while (
    $expr1
    && $expr2
) {
    //
}

do {
    //
} while (
    $expr1
    && $expr2
);

```

### for

```php
<?php

for ($i = 0; $i < 10; $i++) {
    //
}

```

> 括号中的表达式 **可能** 会被分开多行，每一行至少要缩进一次。如果这样做，第一个条件 **必须** 在新的一行。右括号和左大括号 **必须** 在同一行，而且中间有一个空格。

```php
<?php

for (
    $i = 0;
    $i < 10;
    $i++
) {
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

### try 和 catch 和 finally

```php
<?php

try {
    //
} catch (FirstExceptionType $e) {
    //
} catch (OtherExceptionType $e) {
    //
} finally {
    //
}

```

## 运算符

> 当运算符周围允许出现空格时， **可以** 出于可读性目的使用多个空格。

### 一元运算符

> 递增运算符和递减运算符与操作数之间 **不得** 有任何空格。

```php
<?php

$i++;
++$j;

```

> 类型转换运算符的圆括号内部 **不得** 有任何空格。

```php
<?php

$intValue = (int) $input;

```

### 二元运算符

> 所有二元运算符 **必须** 在前后跟至少一个空格。

```php
<?php

if ($a === $b) {
    $foo = $bar ?? $a ?? $b;
} elseif ($a > $b) {
    $foo = $a + $b * $c;
}

```

### 三元运算符

```php
<?php

$variable = $foo ? 'foo' : 'bar';

```

> 如果省略条件运算符的中间操作数，运算符 **必须** 遵循与其他二元运算符相同的样式规则。

```php
<?php

$variable = $foo ?: 'bar';

```

## 闭包

> 闭包声明时，关键字 `function` 后以及关键字 `use` 的前后都 **必须** 要有一个空格。
>
> 开始花括号 **必须** 写在声明的同一行，结束花括号 **必须** 紧跟主体结束的下一行。
>
> 参数列表和变量列表的左括号后以及右括号前， **一定不可** 有空格。
>
> 参数和变量列表中，逗号前 **一定不可** 有空格，而逗号后 **必须** 要有空格。
>
> 闭包中有默认值的参数 **必须** 放到列表的后面。
>
> 如果声明了返回类型，它 **必须** 遵循普通函数和方法相同的规则，如果使用 `use` 关键字，冒号 **必须** 在 `use` 右括号后且冒号前后不能有空格。

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
    //
};

/**
 * Just a test function.
 *
 * @param  int    $arg1
 * @param  string $arg2
 * @return void
 */
$closureWithArgsAndVars = function (int $arg1, string $arg2) use ($var1, $var2) {
    //
};

/**
 * Just a test function.
 *
 * @param  int    $arg1
 * @param  string $arg2
 * @return string
 */
$closureWithArgsVarsAndReturn = function (int $arg1, string $arg2) use ($var1, $var2): string {
    return 'foo';
};

```

> 参数和变量 **可以** 分多行放置，此时第一项 **必须** 放在下一行，并且每行只能有一个参数或变量。
>
> 结束多行列表的时候，右括号和左大括号 **必须** 要放在一行，而且中间有一个空格。

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
    //
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
    //
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
    //
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
    //
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
    //
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

## 匿名类

> 匿名类 **必须** 遵循和闭包一样的规范。

```php
<?php

$instance = new class {};

```

> 如果接口列表不换行，左花括号 **可以** 在同一行，如果接口列表换行，左花括号 **必须** 放在最后一个接口的下一行。

```php
<?php

$instance = new class extends \Foo implements \HandleableInterface {
    //
};

$instance = new class extends \Foo implements
    \ArrayAccess,
    \Countable,
    \Serializable
{
    //
};

```

