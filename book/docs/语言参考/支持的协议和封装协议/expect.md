# expect://

由 `expect://` 封装协议打开的数据流 PTY 提供了对进程 `stdio` 、 `stdout` 和 `stderr` 的访问。

|           属性            | 支持 |
| :-----------------------: | :--: |
| 受 `allow_url_fopen` 限制 |  No  |
|         允许读取          | Yes  |
|         允许写入          | Yes  |
|         允许添加          | Yes  |
|      允许同时读和写       |  No  |
|       支持 `stat()`       |  No  |
|      支持 `unlink()`      |  No  |
|      支持 `rename()`      |  No  |
|      支持 `mkdir()`       |  No  |
|      支持 `rmdir()`       |  No  |