# cURL

* [cURL](#curl)
  * [curl_close - 关闭 cURL 会话](#curlclose)
  * [curl_copy_handle - 复制一个 cURL 句柄和它的所有选项](#curlcopyhandle)
  * [curl_errno - 返回最后一次的错误代码](#curlerrno)
  * [curl_error - 返回当前会话最后一次错误的字符串](#curlerror)
  * [curl_escape - 使用 URL 编码给定的字符串](#curlescape)
  * [curl_exec - 执行 cURL 会话](#curlexec)
  * [curl_file_create - 创建一个 CURLFile 对象](#curlfilecreate)
  * [curl_getinfo - 获取一个 cURL 连接资源句柄的信息](#curlgetinfo)
  * [curl_init - 初始化 cURL 会话](#curlinit)
  * [curl_multi_add_handle - 向 cURL 批处理会话中添加单独的 cURL 句柄](#curlmultiaddhandle)
  * [curl_multi_close - 关闭一组 cURL 句柄](#curlmulticlose)
  * [curl_multi_errno - 返回上一次 cURL 批处理的错误码](#curlmultierrno)
  * [curl_multi_exec - 运行当前 cURL 句柄的子连接](#curlmultiexec)
  * [curl_multi_getcontent - 返回获取的输出的文本流](#curlmultigetcontent)
  * [curl_multi_info_read - 获取当前解析的 cURL 的相关传输信息](#curlmultiinforead)
  * [curl_multi_init - 返回一个新 cURL 批处理句柄](#curlmultiinit)
  * [curl_multi_remove_handle - 移除 cURL 批处理句柄资源中的某个句柄资源](#curlmultiremovehandle)
  * [curl_multi_select - 等待所有 cURL 批处理中的活动连接](#curlmultiselect)
  * [curl_multi_setopt - 为 cURL 并行处理设置一个选项](#curlmultisetopt)
  * [curl_multi_strerror - 返回字符串描述的错误代码](#curlmultistrerror)
  * [curl_pause - 暂停和取消暂停一个连接](#curlpause)
  * [curl_reset - 重置一个 libcurl 会话句柄的所有的选项](#curlreset)
  * [curl_setopt_array - 为 cURL 传输会话批量设置选项](#curlsetoptarray)
  * [curl_setopt - 设置 cURL 传输选项](#curlsetopt)
  * [curl_share_close - 关闭 cURL 共享句柄](#curlshareclose)
  * [curl_share_errno - 返回共享 curl 句柄的最后一次错误号](#curlshareerrno)
  * [curl_share_init - 初始化一个 cURL 共享句柄](#curlshareinit)
  * [curl_share_setopt - 为 cURL 共享句柄设置选项](#curlsharesetopt)
  * [curl_share_strerror - 返回错误号对应的错误消息](#curlsharestrerror)
  * [curl_strerror - 返回错误代码的字符串描述](#curlstrerror)
  * [curl_unescape - 解码给定的 URL 编码的字符串](#curlunescape)
  * [curl_version - 获取 cURL 版本信息](#curlversion)
* [CURLFile](#curlfile)
  * [CURLFile::__construct - 创建 CURLFile 对象](#curlfileconstruct)
  * [CURLFile::getFilename - 获取被上传文件的文件名](#curlfilegetfilename)
  * [CURLFile::getMimeType - 获取被上传文件的 MIME 类型](#curlfilegetmimetype)
  * [CURLFile::getPostFilename - 获取 POST 请求时使用的文件名](#curlfilegetpostfilename)
  * [CURLFile::setMimeType - 设置被上传文件的 MIME 类型](#curlfilesetmimetype)
  * [CURLFile::setPostFilename - 设置 POST 请求时使用的文件名](#curlfilesetpostfilename)

## cURL

### curl_close

```php
<?php

curl_close(curl_init());

```

### curl_copy_handle

```php
<?php

var_dump(curl_copy_handle(curl_init())); // resource(5) of type (curl)

```

### curl_errno

```php
<?php

var_dump(curl_errno(curl_init())); // int(0)

```

### curl_error

```php
<?php

var_dump(curl_error(curl_init())); // string(0) ""

```

### curl_escape

```php
<?php

var_dump(curl_escape(curl_init(), 'foo=foo')); // string(9) "foo%3Dfoo"

```

### curl_exec

```php
<?php

var_dump(curl_exec(curl_init())); // bool(false)

$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'http://www.example.com');
var_dump(curl_exec($ch));         // bool(true)

```

### curl_file_create

```php
<?php

var_dump(curl_file_create(__DIR__ . '/example.txt'));

```

### curl_getinfo

```php
<?php

var_dump(curl_getinfo(curl_init()));
var_dump(curl_getinfo(curl_init(), CURLINFO_CONNECT_TIME));

```

### curl_init

```php
<?php

var_dump(curl_init());                         // resource(4) of type (curl)
var_dump(curl_init('http://www.example.com')); // resource(5) of type (curl)

```

### curl_multi_add_handle

```php
<?php

$mh = curl_multi_init();
$ch1 = curl_init();
$ch2 = curl_init();
var_dump(curl_multi_add_handle($mh, $ch1)); // int(0)
var_dump(curl_multi_add_handle($mh, $ch2)); // int(0)

```

### curl_multi_close

```php
<?php

curl_multi_close(curl_multi_init());

```

### curl_multi_errno

```php
<?php

var_dump(curl_multi_errno(curl_multi_init())); // int(0)

```

### curl_multi_exec

```php
<?php

$mh = curl_multi_init();
$ch1 = curl_init();
curl_setopt($ch1, CURLOPT_URL, 'http://www.example.com');
$ch2 = curl_init();
curl_setopt($ch2, CURLOPT_URL, 'http://www.example.com');
curl_multi_add_handle($mh, $ch1);
curl_multi_add_handle($mh, $ch2);

do {
    $status = curl_multi_exec($mh, $still_running);
} while ($status === CURLM_CALL_MULTI_PERFORM || $still_running);

```

### curl_multi_getcontent

```php
<?php

$mh = curl_multi_init();
$ch1 = curl_init();
curl_setopt($ch1, CURLOPT_URL, 'http://www.example.com');
curl_setopt($ch1, CURLOPT_RETURNTRANSFER, true);
$ch2 = curl_init();
curl_setopt($ch2, CURLOPT_URL, 'http://www.example.com');
curl_setopt($ch2, CURLOPT_RETURNTRANSFER, true);
curl_multi_add_handle($mh, $ch1);
curl_multi_add_handle($mh, $ch2);

do {
    $status = curl_multi_exec($mh, $still_running);
    $info = curl_multi_info_read($mh);
    if ($info !== false) {
        var_dump(curl_multi_getcontent($info['handle']));
    }
} while ($status === CURLM_CALL_MULTI_PERFORM || $still_running);

```

### curl_multi_info_read

```php
<?php

$mh = curl_multi_init();
$ch1 = curl_init();
curl_setopt($ch1, CURLOPT_URL, 'http://www.example.com');
$ch2 = curl_init();
curl_setopt($ch2, CURLOPT_URL, 'http://www.example.com');
curl_multi_add_handle($mh, $ch1);
curl_multi_add_handle($mh, $ch2);

do {
    $status = curl_multi_exec($mh, $still_running);
    $info = curl_multi_info_read($mh);
    if ($info !== false) {
        var_dump($info);
    }
} while ($status === CURLM_CALL_MULTI_PERFORM || $still_running);
// array(3) { ["msg"]=> int(1) ["result"]=> int(0) ["handle"]=> resource(4) of type (curl) }
// array(3) { ["msg"]=> int(1) ["result"]=> int(0) ["handle"]=> resource(3) of type (curl) }

```

### curl_multi_init

```php
<?php

var_dump(curl_multi_init()); // resource(4) of type (curl_multi)

```

### curl_multi_remove_handle

```php
<?php

$mh = curl_multi_init();
$ch1 = curl_init();
$ch2 = curl_init();
curl_multi_add_handle($mh, $ch1);
curl_multi_add_handle($mh, $ch2);
var_dump(curl_multi_remove_handle($mh, $ch1)); // int(0)
var_dump(curl_multi_remove_handle($mh, $ch2)); // int(0)

```

### curl_multi_select

```php
<?php

var_dump(curl_multi_select(curl_multi_init(), 1)); // int(0)

```

### curl_multi_setopt

```php
<?php

var_dump(curl_multi_setopt(curl_multi_init(), CURLMOPT_MAXCONNECTS, 10)); // bool(true)

```

### curl_multi_strerror

```php
<?php

var_dump(curl_multi_strerror(curl_multi_errno(curl_multi_init()))); // string(8) "No error"

```

### curl_pause

```php
<?php

var_dump(curl_pause(curl_init(), CURLPAUSE_ALL)); // int(0)

```

### curl_reset

```php
<?php

$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'http://example.com');
curl_reset($ch);
curl_setopt($ch, CURLOPT_URL, 'http://www.example.com');

```

### curl_setopt_array

```php
<?php

$options = [
    CURLOPT_URL            => 'http://www.example.com',
    CURLOPT_RETURNTRANSFER => true
];
var_dump(curl_setopt_array(curl_init(), $options)); // bool(true)

```

### curl_setopt

```php
<?php

$ch = curl_init();
var_dump(curl_setopt($ch, CURLOPT_URL, 'http://www.example.com')); // bool(true)
var_dump(curl_setopt($ch, CURLOPT_RETURNTRANSFER, true));          // bool(true)

```

### curl_share_close

```php
<?php

curl_share_close(curl_share_init());

```

### curl_share_errno

```php
<?php

var_dump(curl_share_errno(curl_share_init())); // int(0)

```

### curl_share_init

```php
<?php

var_dump(curl_share_init()); // resource(4) of type (curl_share)

```

### curl_share_setopt

```php
<?php

$ch = curl_share_init();
var_dump(curl_share_setopt($ch, CURLSHOPT_SHARE, CURL_LOCK_DATA_COOKIE)); // bool(true)

```

### curl_share_strerror

```php
<?php

var_dump(curl_share_strerror(curl_share_errno(curl_share_init()))); // string(8) "No error"

```

### curl_strerror

```php
<?php

var_dump(curl_strerror(curl_errno(curl_init()))); // string(8) "No error"

```

### curl_unescape

```php
<?php

var_dump(curl_unescape(curl_init(), 'foo%3Dfoo')); // string(7) "foo=foo"

```

### curl_version

```php
<?php

var_dump(curl_version());

```

## CURLFile

### CURLFile::__construct

```php
<?php

var_dump(new CURLFile(__DIR__ . '/example.txt'));                          // object(CURLFile)#1 (3) { ["name"]=> string(40) "C:\Project\nginx-1.15.8\html/example.txt" ["mime"]=> string(0) "" ["postname"]=> string(0) "" }
var_dump(new CURLFile(__DIR__ . '/example.txt', 'text/plain', 'example')); // object(CURLFile)#1 (3) { ["name"]=> string(40) "C:\Project\nginx-1.15.8\html/example.txt" ["mime"]=> string(10) "text/plain" ["postname"]=> string(7) "example" }

```

### CURLFile::getFilename

```php
<?php

$file = new CURLFile(__DIR__ . '/example.txt', 'text/plain', 'example');
var_dump($file->getFilename());

```

### CURLFile::getMimeType

```php
<?php

$file = new CURLFile(__DIR__ . '/example.txt', 'text/plain', 'example');
var_dump($file->getMimeType()); // string(10) "text/plain"

```

### CURLFile::getPostFilename

```php
<?php

$file = new CURLFile(__DIR__ . '/example.txt', 'text/plain', 'example');
var_dump($file->getPostFilename()); // string(7) "example"

```

### CURLFile::setMimeType

```php
<?php

$file = new CURLFile(__DIR__ . '/example.txt', 'text/plain', 'example');
$file->setMimeType('image/jpeg');
var_dump($file->getMimeType()); // string(10) "image/jpeg"

```

### CURLFile::setPostFilename

```php
<?php

$file = new CURLFile(__DIR__ . '/example.txt', 'text/plain', 'example');
$file->setPostFilename('index');
var_dump($file->getPostFilename()); // string(5) "index"

```

