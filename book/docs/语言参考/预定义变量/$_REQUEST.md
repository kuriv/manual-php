# $_REQUEST

`$_REQUEST` 是一个默认情况下包含了 `$_GET` ， `$_POST` 和 `$_COOKIE` 的数组。

```php
<?php

var_dump($_REQUEST['foo']);

```

当访问 [http://localhost/?foo=foo](http://localhost/?foo=foo) 时，以上例程的输出类似于：

```
string(3) "foo"
```

假设用户通过 HTTP POST 方式传递了参数 `foo=foo` ，以上例程的输出类似于：

```
string(3) "foo"
```

假设之前发送了 `foo=foo` 的 Cookie ，以上例程的输出类似于：

```
string(3) "foo"
```

