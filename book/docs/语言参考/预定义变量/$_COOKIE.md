# $_COOKIE

`$_COOKIE` 是一个通过 HTTP Cookie 方式传递给当前脚本的变量的数组。

```php
<?php

var_dump($_COOKIE['foo']);

```

假设之前发送了 `foo=foo` 的 Cookie ，以上例程的输出类似于：

```
string(3) "foo"
```

