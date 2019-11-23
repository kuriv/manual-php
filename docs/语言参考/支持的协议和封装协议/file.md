# file://

文件系统是 PHP 使用的默认封装协议，展现了本地文件系统。 当指定了一个相对路径（不以 `/` 、 `\` 、 `\\` 或 Windows 盘符开头的路径），提供的路径将基于当前的工作目录。在很多情况下是脚本所在的目录，除非被修改了。使用 CLI 的时候，目录默认是脚本被调用时所在的目录。在某些函数里，例如 `fopen()` 函数和 `file_get_contents()` 函数， `include_path` 会可选地搜索，也作为相对的路径。

|           属性            | 支持 |
| :-----------------------: | :--: |
| 受 `allow_url_fopen` 影响 |  No  |
|         允许读取          | Yes  |
|         允许写入          | Yes  |
|         允许添加          | Yes  |
|      允许同时读和写       | Yes  |
|       支持 `stat()`       | Yes  |
|      支持 `unlink()`      | Yes  |
|      支持 `rename()`      | Yes  |
|      支持 `mkdir()`       | Yes  |
|      支持 `rmdir()`       | Yes  |

```php
<?php

$handle = fopen('example.php', 'a');
$handle = fopen(__DIR__ . '/example.php', 'a');
$data = file_get_contents('example.php');
$data = file_get_contents(__DIR__ . '/example.php');

```

