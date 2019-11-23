# $_POST

当 HTTP POST 请求的 Content-Type 是 application/x-www-form-urlencoded 或 multipart/form-data 时，会将变量以关联数组形式传入当前脚本。

```php
<?php

var_dump($_POST['foo']);

```

假设用户通过 HTTP POST 方式传递了参数 `foo=foo` ，以上例程的输出类似于：

```
string(3) "foo"
```

