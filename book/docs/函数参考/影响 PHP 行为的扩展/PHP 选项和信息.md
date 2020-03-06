# PHP 选项和信息

* [assert_options - 设置 / 获取断言的各种标志](#assertoptions)
* [assert - 检查一个断言是否为 false](#assert)
* [cli_get_process_title - 返回当前进程的标题](#cligetprocesstitle)
* [cli_set_process_title - 设置进程标题](#clisetprocesstitle)
* [extension_loaded - 检查一个扩展是否已经加载](#extensionloaded)
* [gc_collect_cycles - 强制收集所有现存的垃圾循环周期](#gccollectcycles)
* [gc_disable - 停用垃圾收集器](#gcdisable)
* [gc_enable - 激活垃圾收集器](#gcenable)
* [gc_enabled - 返回垃圾收集器的状态](#gcenabled)
* [gc_mem_caches - 回收 Zend Engine 内存管理器使用的内存](#gcmemcaches)
* [gc_status - 获取有关垃圾收集器的信息](#gcstatus)
* [get_cfg_var - 获取 PHP 配置选项的值](#getcfgvar)
* [get_current_user - 获取当前 PHP 脚本所有者名称](#getcurrentuser)
* [get_defined_constants - 返回所有常量的关联数组，键是常量名，值是常量值](#getdefinedconstants)
* [get_extension_funcs - 返回模块函数名称的数组](#getextensionfuncs)
* [get_include_path - 获取当前的 include_path 配置选项](#getincludepath)
* [get_included_files - 返回被 include 和 require 文件名的数组](#getincludedfiles)
* [get_loaded_extensions - 返回所有编译并加载模块名的数组](#getloadedextensions)
* [get_required_files - 返回被 include 和 require 文件名的数组](#getrequiredfiles)
* [get_resources - 返回活动的资源](#getresources)
* [getenv - 获取一个环境变量的值](#getenv)
* [getlastmod - 获取页面最后修改的时间](#getlastmod)
* [getmygid - 获取当前 PHP 脚本拥有者的 GID](#getmygid)
* [getmyinode - 获取当前脚本的索引节点](#getmyinode)
* [getmypid - 获取 PHP 进程的 ID](#getmypid)
* [getmyuid - 获取 PHP 脚本所有者的 UID](#getmyuid)
* [getopt - 从命令行参数列表中获取选项](#getopt)
* [getrusage - 获取当前资源使用状况](#getrusage)
* [ini_alter - 为一个配置选项设置值](#inialter)
* [ini_get_all - 获取所有配置选项](#inigetall)
* [ini_get - 获取一个配置选项的值](#iniget)
* [ini_restore - 恢复配置选项的值](#inirestore)
* [ini_set - 为一个配置选项设置值](#iniset)
* [memory_get_peak_usage - 返回分配给 PHP 内存的峰值](#memorygetpeakusage)
* [memory_get_usage - 返回分配给 PHP 的内存量](#memorygetusage)
* [php_ini_loaded_file - 取得已加载的 php.ini 文件的路径](#phpiniloadedfile)
* [php_ini_scanned_files - 返回从额外 ini 目录里解析的 .ini 文件列表](#phpiniscannedfiles)
* [php_sapi_name - 返回 Web 服务器和 PHP 之间的接口类型](#phpsapiname)
* [php_uname - 返回运行 PHP 的系统的有关信息](#phpuname)
* [phpcredits - 打印 PHP 贡献者名单](#phpcredits)
* [phpinfo - 输出关于 PHP 配置的信息](#phpinfo)
* [phpversion - 获取当前的 PHP 版本](#phpversion)
* [putenv - 设置环境变量的值](#putenv)
* [set_include_path - 设置 include_path 配置选项](#setincludepath)
* [set_time_limit - 设置脚本最大执行时间](#settimelimit)
* [sys_get_temp_dir - 返回用于临时文件的目录](#sysgettempdir)
* [version_compare - 对比两个 PHP 规范化的版本数字字符串](#versioncompare)
* [zend_thread_id - 返回当前线程的唯一识别符](#zendthreadid)
* [zend_version - 获取当前 Zend 引擎的版本](#zendversion)

## assert_options

```php
<?php

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    echo 'Assert failed';
}

assert_options(ASSERT_ACTIVE, true);
assert_options(ASSERT_WARNING, true);
assert_options(ASSERT_BAIL, true);
assert_options(ASSERT_QUIET_EVAL, false);
assert_options(ASSERT_CALLBACK, 'foo');

```

## assert

```php
<?php

assert(true == false);                                           // PHP Warning:  assert(): assert(true == false) failed
assert(true == false, 'True is not false!');                     // PHP Warning:  assert(): True is not false!
assert(true == false, new AssertionError('True is not false!')); // PHP Warning:  assert(): AssertionError: True is not false!

```

## cli_get_process_title

```php
<?php

var_dump(cli_get_process_title());

```

## cli_set_process_title

```php
<?php

var_dump(cli_set_process_title('Hello World!')); // bool(true)

```

## extension_loaded

```php
<?php

var_dump(extension_loaded('mbstring'));

```

## gc_collect_cycles

```php
<?php

var_dump(gc_collect_cycles());

```

## gc_disable

```php
<?php

gc_disable();

```

## gc_enable

```php
<?php

gc_enable();

```

## gc_enabled

```php
<?php

var_dump(gc_enabled());

```

## gc_mem_caches

```php
<?php

var_dump(gc_mem_caches());

```

## gc_status

```php
<?php

var_dump(gc_status());

```

## get_cfg_var

```php
<?php

var_dump(get_cfg_var('display_errors'));

```

## get_current_user

```php
<?php

var_dump(get_current_user());

```

## get_defined_constants

```php
<?php

var_dump(get_defined_constants());
var_dump(get_defined_constants(true));

```

## get_extension_funcs

```php
<?php

var_dump(get_extension_funcs('mbstring'));

```

## get_include_path

```php
<?php

var_dump(get_include_path());

```

## get_included_files

```php
<?php

var_dump(get_included_files());

```

## get_loaded_extensions

```php
<?php

var_dump(get_loaded_extensions());
var_dump(get_loaded_extensions(true));

```

## get_required_files

```php
<?php

var_dump(get_required_files());

```

## get_resources

```php
<?php

var_dump(get_resources());
var_dump(get_resources('stream'));

```

## getenv

```php
<?php

var_dump(getenv('foo'));
var_dump(getenv('bar'));

```

## getlastmod

```php
<?php

var_dump(getlastmod());

```

## getmygid

```php
<?php

var_dump(getmygid());

```

## getmyinode

```php
<?php

var_dump(getmyinode());

```

## getmypid

```php
<?php

var_dump(getmypid());

```

## getmyuid

```php
<?php

var_dump(getmyuid());

```

## getopt

```
php example.php -a foo -b bar
```

当执行上面的命令时，会输出下面的结果：

```
array(2) {
  ["a"]=>
  string(3) "foo"
  ["b"]=>
  string(3) "bar"
}
```

上例中的 `example.php` 文件内容：

```php
<?php

var_dump(getopt('a:b:'));

```

---

```
php example.php -a foo -b bar --baz baz --qux qux
```

当执行上面的命令时，会输出下面的结果：

```
array(4) {
  ["a"]=>
  string(3) "foo"
  ["b"]=>
  string(3) "bar"
  ["baz"]=>
  string(3) "baz"
  ["qux"]=>
  string(3) "qux"
}
```

上例中的 `example.php` 文件内容：

```php
<?php

var_dump(getopt('a:b:', ['baz:', 'qux:']));

```

## getrusage

```php
<?php

var_dump(getrusage());

```

## ini_alter

```php
<?php

var_dump(ini_alter('display_errors', '0'));

```

## ini_get_all

```php
<?php

var_dump(ini_get_all());
var_dump(ini_get_all('mbstring'));
var_dump(ini_get_all('mbstring', false));

```

## ini_get

```php
<?php

var_dump(ini_get('display_errors'));

```

## ini_restore

```php
<?php

ini_set('display_errors', '0');
ini_restore('display_errors');

```

## ini_set

```php
<?php

var_dump(ini_set('display_errors', '0'));

```

## memory_get_peak_usage

```php
<?php

var_dump(memory_get_peak_usage());
var_dump(memory_get_peak_usage(true));

```

## memory_get_usage

```php
<?php

var_dump(memory_get_usage());
var_dump(memory_get_usage(true));

```

## php_ini_loaded_file

```php
<?php

var_dump(php_ini_loaded_file());

```

## php_ini_scanned_files

```php
<?php

var_dump(php_ini_scanned_files());

```

## php_sapi_name

```php
<?php

var_dump(php_sapi_name());

```

## php_uname

```php
<?php

var_dump(php_uname());

```

## phpcredits

```php
<?php

phpcredits();

```

## phpinfo

```php
<?php

phpinfo();
phpinfo(INFO_ALL);
phpinfo(INFO_GENERAL);
phpinfo(INFO_CREDITS);
phpinfo(INFO_CONFIGURATION);
phpinfo(INFO_MODULES);
phpinfo(INFO_ENVIRONMENT);
phpinfo(INFO_VARIABLES);
phpinfo(INFO_LICENSE);

```

## phpversion

```php
<?php

var_dump(phpversion());
var_dump(phpversion('mbstring'));

```

## putenv

```php
<?php

var_dump(putenv('foo=foo')); // bool(true)
var_dump(putenv('bar=bar')); // bool(true)

```

## set_include_path

```php
<?php

var_dump(set_include_path(__DIR__));

```

## set_time_limit

```php
<?php

var_dump(set_time_limit(30)); // bool(true)
var_dump(set_time_limit(0));  // bool(true)

```

## sys_get_temp_dir

```php
<?php

var_dump(sys_get_temp_dir());

```

## version_compare

```php
<?php

var_dump(version_compare('7.4.0', '7.4.0'));       // int(0)
var_dump(version_compare('7.4.1', '7.4.0'));       // int(1)
var_dump(version_compare('7.4.0', '7.4.1'));       // int(-1)
var_dump(version_compare('7.4.0', '7.4.0', '==')); // bool(true)
var_dump(version_compare('7.4.1', '7.4.0', '>'));  // bool(true)
var_dump(version_compare('7.4.0', '7.4.1', '<=')); // bool(true)
var_dump(version_compare(PHP_VERSION, '7.4.0'));

```

## zend_thread_id

```php
<?php

var_dump(zend_thread_id());

```

## zend_version

```php
<?php

var_dump(zend_version());

```

