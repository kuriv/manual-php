# ssh2://

|           属性            | ssh2.shell | ssh2.exec | ssh2.tunnel | ssh2.sftp | ssh2.scp |
| :-----------------------: | :--------: | :---------: | :-----------: | :---------: | :--------: |
| 受 `allow_url_fopen` 限制 |    Yes     | Yes       | Yes         | Yes       | Yes      |
|         允许读取          |    Yes     | Yes       | Yes         | Yes       | Yes      |
|         允许写入          |    Yes     | Yes       | Yes         | Yes       | No       |
|         允许添加          |     No     | No        | No          | Yes       | No       |
|      允许同时读和写       |    Yes     | Yes       | Yes         | Yes       | No       |
|       支持 `stat()`       |     No     | No        | No          | Yes       | No       |
|      支持 `unlink()`      |     No     | No        | No          | Yes       | No       |
|      支持 `rename()`      |     No     | No        | No          | Yes       | No       |
|      支持 `mkdir()`       |     No     | No        | No          | Yes       | No       |
|      支持 `rmdir()`       |     No     | No        | No          | Yes       | No       |