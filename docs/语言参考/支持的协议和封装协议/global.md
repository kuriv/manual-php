# global://

|           属性            | 支持 |
| :-----------------------: | :--: |
| 受 `allow_url_fopen` 限制 |  No  |
| 受 `allow_url_include` 限制 |  No  |
|         允许读取          | No |
|         允许写入          | No |
|         允许添加          |  No  |
|      允许同时读和写       |  No  |
|       支持 `stat()`       |  No  |
|      支持 `unlink()`      |  No  |
|      支持 `rename()`      |  No  |
|      支持 `mkdir()`       |  No  |
|      支持 `rmdir()`       |  No  |

```php
<?php

$files = new DirectoryIterator('glob://ext/spl/*.php');
foreach ($files as $file) {
    var_dump($file->getFilename(), $file->getSize());
}

```

