# php://

* [php://stdin php://stdout php://stderr](#phpstdin-phpstdout-phpstderr)
* [php://input](#phpinput)
* [php://output](#phpoutput)
* [php://fd](#phpfd)
* [php://memory php://temp](#phpmemory-phptemp)
* [php://filter](#phpfilter)

|           属性            |                    支持                    |
| :-----------------------: | :----------------------------------------: |
| 受 `allow_url_fopen` 限制 |                     No                     |
| 受 `allow_url_include` 限制 |                     `php://input`<br>`php://stdin`<br/>`php://memory`<br/>`php://temp`                     |
|         允许读取          | `php://stdin`<br/>`php://input`<br/>`php://fd`<br/>`php://memory`<br/>`php://temp` |
|         允许写入          |                     `php://stdout`<br/>`php://stderr`<br/>`php://output`<br/>`php://fd`<br/>`php://memory`<br/>`php://temp`                     |
|         允许添加          |                     `php://stdout`<br/>`php://stderr`<br/>`php://output`<br/>`php://fd`<br/>`php://memory`<br/>`php://temp`                     |
|      允许同时读和写       | `php://fd`<br/>`php://memory`<br/>`php://temp` |
|       支持 `stat()`       |       `php://memory`<br/>`php://temp`   |
|      支持 `unlink()`      |                     No                     |
|      支持 `rename()`      |                     No                     |
|      支持 `mkdir()`       |                     No                     |
|      支持 `rmdir()`       |                     No                     |
|      仅仅支持 `stream_select()`      |                     `php://stdin`<br/>`php://stdout`<br/>`php://stderr`<br/>`php://fd`<br/>`php://temp`                     |

## php://stdin php://stdout php://stderr

`php://stdin` 、 `php://stdout` 和 `php://stderr` 允许直接访问 PHP 进程相应的输入或者输出流。数据流引用了复制的文件描述符，所以如果打开 `php://stdin` 并在之后关了它，仅是关闭了复制品，真正被引用的 STDIN 并不受影响。 `php://stdin` 是只读的， `php://stdout` 和 `php://stderr` 是只写的。

## php://input

`php://input` 是个可以访问请求的原始数据的只读流。

## php://output

`php://output` 是一个只写的数据流，允许以 `print` 和 `echo` 一样的方式写入到输出缓冲区。

## php://fd

`php://fd` 允许直接访问指定的文件描述符，例如 `php://fd/3` 引用了文件描述符 3 。

## php://memory php://temp

`php://memory` 和 `php://temp` 是一个类似文件包装器的数据流，允许读写临时数据。两者的唯一区别是 `php://memory` 总是把数据储存在内存中，而 `php://temp` 会在内存量达到预定义的限制后存入临时文件中。

## php://filter

`php://filter` 是一种元封装器，用于数据流打开时的筛选过滤应用。