# $_FILES

`$_FILES` 是通过 HTTP POST 方式上传到当前脚本的项目的数组。

```php
<?php

var_dump($_FILES['foo']);

```

假设用户通过 HTTP POST 方式上传了 `foo.txt` 文件，以上例程的输出类似于：

```
array(5) {
  ["name"]=>
  string(7) "foo.txt"
  ["type"]=>
  string(10) "text/plain"
  ["tmp_name"]=>
  string(0) ""
  ["error"]=>
  int(0)
  ["size"]=>
  int(0)
}
```

