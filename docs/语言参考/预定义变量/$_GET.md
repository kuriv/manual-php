# $_GET

`$_GET` 是一个通过 URL 参数传递给当前脚本的变量的数组。

```php
<?php

var_dump($_GET['foo']);

```

当访问 [http://localhost/?foo=foo](http://localhost/?foo=foo) 时，以上例程的输出类似于：

```
string(3) "foo"
```

