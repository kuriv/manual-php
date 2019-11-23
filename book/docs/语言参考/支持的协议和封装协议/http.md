# http://

允许通过 HTTP 的 GET 方法，以只读访问文件或资源。 HTTP 请求会附带一个 Host 头，用于兼容基于域名的虚拟主机。 如果在 `php.ini` 文件中或字节流上下文配置了 `user_agent` 字符串，它也会被包含在请求之中。数据流允许读取资源的 `body` ，而 `headers` 则储存在了 `$http_response_header` 变量里。

|           属性            | 支持 |
| :-----------------------: | :--: |
| 受 `allow_url_fopen` 限制 | Yes  |
|         允许读取          | Yes  |
|         允许写入          |  No  |
|         允许添加          |  No  |
|      允许同时读和写       | N/A  |
|       支持 `stat()`       |  No  |
|      支持 `unlink()`      |  No  |
|      支持 `rename()`      |  No  |
|      支持 `mkdir()`       |  No  |
|      支持 `rmdir()`       |  No  |

```php
<?php

$data = file_get_contents('https://github.com/');

```

