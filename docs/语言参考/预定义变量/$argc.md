# $argc

`$argc` 是包含当运行于命令行下时传递给当前脚本的参数的数目。

```php
<?php

var_dump($argc);

```

当执行 `php index.php foo bar` 这条命令时，以上例程的输出类似于：

```
int(3)
```

