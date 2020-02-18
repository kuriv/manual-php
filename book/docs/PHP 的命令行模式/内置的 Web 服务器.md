# 内置的 Web 服务器

* [启动 Web 服务器](#启动-web-服务器)
* [启动时指定根目录](#启动时指定根目录)
* [使用路由脚本](#使用路由脚本)

## 启动 Web 服务器

切换到网站根目录，执行下面的命令可以启动 Web 服务器，访问 [http://localhost:8080/](http://localhost:8080/) 即可预览网站。

```
php -S localhost:8080
```

## 启动时指定根目录

也可以执行下面的命令来指定网站根目录。

```
php -S localhost:8080 -t C:/Project/nginx-1.14.2/html/
```

## 使用路由脚本

如果在启动 Web 服务器的时候指定了一个 PHP 文件，则这个文件会作为一个路由脚本，意味着每次请求都会先执行这个脚本。

```
php -S localhost:8080 router.php
```

如果这个路由脚本返回 `false` ，那么直接返回请求的文件，例如请求静态文件不作任何处理。否则会把输出返回到浏览器。

```php
<?php

$uri = urldecode(parse_url($_SERVER['REQUEST_URI'], PHP_URL_PATH));
if ($uri !== '/' && file_exists(__DIR__ . $uri)) {
    return false;
}
echo 'Loading...';

```

