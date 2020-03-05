# data://

|           属性            | 支持 |
| :-----------------------: | :--: |
| 受 `allow_url_fopen` 限制 |  No  |
| 受 `allow_url_include` 限制 |  Yes  |
|         允许读取          | Yes  |
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

var_dump(file_get_contents('data://text/plain;base64,UEhQ')); // string(3) "PHP"

$handle = fopen('data://text/plain;base64,', 'r');
$meta = stream_get_meta_data($handle);
var_dump($meta['mediatype']);                                 // string(10) "text/plain"

```

