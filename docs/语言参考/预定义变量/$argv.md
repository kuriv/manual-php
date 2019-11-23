# $argv

`$argv` 是包含当运行于命令行下时传递给当前脚本的参数的数组。

```php
<?php

var_dump($argv);

```

当执行 `php index.php foo bar` 这条命令时，以上例程的输出类似于：

```
array(3) {
  [0]=>
  string(9) "index.php"
  [1]=>
  string(3) "foo"
  [2]=>
  string(3) "bar"
}
```

