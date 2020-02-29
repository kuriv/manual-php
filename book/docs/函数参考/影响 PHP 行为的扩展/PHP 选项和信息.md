# PHP 选项和信息

* 

## assert_options

```php

```

## assert

```php

```

## cli_get_process_title

```php

```

## cli_set_process_title

```php

```

## dl

```php

```

## extension_loaded

```php

```

## gc_collect_cycles

```php

```

## gc_disable

```php

```

## gc_enable

```php

```

## gc_enabled

```php

```

## gc_mem_caches

```php

```

## gc_status

```php

```

## get_cfg_var

```php

```

## get_current_user

```php

```

## get_defined_constants

```php

```

## get_extension_funcs

```php

```

## get_include_path

```php

```

## get_included_files

```php

```

## get_loaded_extensions

```php

```

## get_magic_quotes_gpc

```php

```

## get_magic_quotes_runtime

```php

```

## get_required_files

```php

```

## get_resources

```php

```

## getenv

```php

```

## getlastmod

```php

```

## getmygid

```php

```

## getmyinode

```php

```

## getmypid

```php

```

## getmyuid

```php

```

## getopt

```php

```

## getrusage

```php

```

## ini_alter

```php

```

## ini_get_all

```php

```

## ini_get

```php

```

## ini_restore

```php

```

## ini_set

```php

```

## magic_quotes_runtime

```php

```

## main

```php

```

## memory_get_peak_usage

```php

```

## memory_get_usage

```php

```

## php_ini_loaded_file

```php

```

## php_ini_scanned_files

```php

```

## php_logo_guid

```php

```

## php_sapi_name

```php

```

## php_uname

```php

```

## phpcredits

```php

```

## phpinfo

```php

```

## phpversion

```php

```

## putenv

```php

```

## restore_include_path

```php

```

## set_include_path

```php

```

## set_magic_quotes_runtime

```php

```

## set_time_limit

```php

```

## sys_get_temp_dir

```php

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

