# $_SESSION

`$_SESSION` 是当前脚本可用 Session 变量的数组。

```php
<?php

session_start();
var_dump($_SESSION['foo']);

```

假设之前保存了 `foo=foo` 的 Session 变量，以上例程的输出类似于：

```
string(3) "foo"
```

