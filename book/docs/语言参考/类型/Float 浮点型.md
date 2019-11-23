# Float 浮点型

浮点型，也叫浮点数，双精度数或实数，可以用以下任一语法定义：

```php
<?php

$foo = 1.001;
$bar = 1.2e3;
$baz = 7e-10;

```

转换为浮点型：

```php
<?php

var_dump((float) -0.0001);        // float(-0.0001)
var_dump((float) 'abc122.34343'); // float(0)
var_dump((float) '122.34343abc'); // float(122.34343)

```

