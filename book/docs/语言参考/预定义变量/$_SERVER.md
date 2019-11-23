# $_SERVER

`$_SERVER` 是一个包含了诸如头信息，路径，以及脚本位置等等信息的数组。这个数组中的项目由 Web 服务器创建。不能保证每个服务器都提供全部项目，服务器可能会忽略一些，或者提供一些没有在这里列举出来的项目。

`$_SERVER['PHP_SELF']` 是当前执行脚本的文件名，与根目录有关 。例如，在地址为 [http://localhost/foo/bar.php](http://localhost/foo/bar.php) 的脚本中使用 `$_SERVER['PHP_SELF']` 将得到 `/foo/bar.php` 。 `$_SERVER['PHP_SELF'] = $_SERVER['SCRIPT_NAME'] + $_SERVER['PATH_INFO']`

```php
<?php

var_dump($_SERVER['PHP_SELF']);

```

`$_SERVER['argv']` 是包含当运行于命令行下时传递给当前脚本的参数的数组。

```php
<?php

var_dump($_SERVER['argv']);

```

`$_SERVER['argc']` 是包含当运行于命令行下时传递给当前脚本的参数的数目。

```php
<?php

var_dump($_SERVER['argc']);

```

`$_SERVER['GATEWAY_INTERFACE']` 是服务器使用的 CGI 规范的版本。

```php
<?php

var_dump($_SERVER['GATEWAY_INTERFACE']);

```

`$_SERVER['SERVER_ADDR']` 是当前运行脚本所在的服务器的 IP 地址。

```php
<?php

var_dump($_SERVER['SERVER_ADDR']);

```

`$_SERVER['SERVER_NAME']` 是当前运行脚本所在的服务器的主机名。

```php
<?php

var_dump($_SERVER['SERVER_NAME']);

```

`$_SERVER['SERVER_SOFTWARE']` 是服务器标识字符串，在响应请求时的头信息中给出。

```php
<?php

var_dump($_SERVER['SERVER_SOFTWARE']);

```

`$_SERVER['SERVER_PROTOCOL']` 是请求页面时通信协议的名称和版本。

```php
<?php

var_dump($_SERVER['SERVER_PROTOCOL']);

```

`$_SERVER['REQUEST_METHOD']` 是访问页面使用的请求方法。例如， GET ， POST ， PUT ， DELETE 。

```php
<?php

var_dump($_SERVER['REQUEST_METHOD']);

```

`$_SERVER['REQUEST_TIME']` 是请求开始时的时间戳。

```php
<?php

var_dump($_SERVER['REQUEST_TIME']);

```

`$_SERVER['REQUEST_TIME_FLOAT']` 是请求开始时的时间戳，微秒级别的精准度。

```php
<?php

var_dump($_SERVER['REQUEST_TIME_FLOAT']);

```

`$_SERVER['QUERY_STRING']` 是页面的查询字符串，如果有的话，通过它进行页面访问。

```php
<?php

var_dump($_SERVER['QUERY_STRING']);

```

`$_SERVER['DOCUMENT_ROOT']` 是当前运行脚本所在的文档根目录。在服务器配置文件中定义。

```php
<?php

var_dump($_SERVER['DOCUMENT_ROOT']);

```

`$_SERVER['HTTP_ACCEPT']` 是当前请求头中 Accept 项的内容，如果存在的话。

```php
<?php

var_dump($_SERVER['HTTP_ACCEPT']);

```

`$_SERVER['HTTP_ACCEPT_CHARSET']` 是当前请求头中 Accept-Charset 项的内容，如果存在的话。

```php
<?php

var_dump($_SERVER['HTTP_ACCEPT_CHARSET']);

```

`$_SERVER['HTTP_ACCEPT_ENCODING']` 是当前请求头中 Accept-Encoding 项的内容，如果存在的话。

```php
<?php

var_dump($_SERVER['HTTP_ACCEPT_ENCODING']);

```

`$_SERVER['HTTP_ACCEPT_LANGUAGE']` 是当前请求头中 Accept-Language 项的内容，如果存在的话。

```php
<?php

var_dump($_SERVER['HTTP_ACCEPT_LANGUAGE']);

```

`$_SERVER['HTTP_CONNECTION']` 是当前请求头中 Connection 项的内容，如果存在的话。

```php
<?php

var_dump($_SERVER['HTTP_CONNECTION']);

```

`$_SERVER['HTTP_HOST']` 是当前请求头中 Host 项的内容，如果存在的话。

```php
<?php

var_dump($_SERVER['HTTP_HOST']);

```

`$_SERVER['HTTP_REFERER']` 是引导用户代理到当前页的前一页的地址（如果存在）。由用户代理设置决定。并不是所有的用户代理都会设置该项，有的还提供了修改 HTTP_REFERER 的功能。简言之，该值并不可信。

```php
<?php

var_dump($_SERVER['HTTP_REFERER']);

```

`$_SERVER['HTTP_USER_AGENT']` 是当前请求头中 User-Agent 项的内容，如果存在的话。该字符串表明了访问该页面的用户代理的信息。除此之外，你可以通过 `get_browser()` 函数来使用该值，从而定制页面输出以便适应用户代理的性能。

```php
<?php

var_dump($_SERVER['HTTP_USER_AGENT']);

```

如果脚本是通过 HTTPS 协议被访问，则被设为一个非空的值。

```php
<?php

var_dump($_SERVER['HTTPS']);

```

`$_SERVER['REMOTE_ADDR']` 是浏览当前页面的用户的 IP 地址。

```php
<?php

var_dump($_SERVER['REMOTE_ADDR']);

```

`$_SERVER['REMOTE_HOST']` 是浏览当前页面的用户的主机名。

```php
<?php

var_dump($_SERVER['REMOTE_HOST']);

```

`$_SERVER['REMOTE_PORT']` 是用户机器上连接到 Web 服务器所使用的端口号。

```php
<?php

var_dump($_SERVER['REMOTE_PORT']);

```

`$_SERVER['REMOTE_USER']` 是经验证的用户。

```php
<?php

var_dump($_SERVER['REMOTE_USER']);

```

`$_SERVER['REDIRECT_REMOTE_USER']` 是验证的用户，如果请求已在内部重定向。

```php
<?php

var_dump($_SERVER['REDIRECT_REMOTE_USER']);

```

`$_SERVER['SCRIPT_FILENAME']` 是当前执行脚本的绝对路径。

```php
<?php

var_dump($_SERVER['SCRIPT_FILENAME']);

```

`$_SERVER['SERVER_ADMIN']` 该值指明了 Apache 服务器配置文件中的 SERVER_ADMIN 参数。

```php
<?php

var_dump($_SERVER['SERVER_ADMIN']);

```

`$_SERVER['SERVER_PORT']` 是 Web 服务器使用的端口。默认值为 80 。如果使用 SSL 安全连接，则这个值为用户设置的 HTTP 端口。

```php
<?php

var_dump($_SERVER['SERVER_PORT']);

```

`$_SERVER['SERVER_SIGNATURE']` 是包含了服务器版本和虚拟主机名的字符串。

```php
<?php

var_dump($_SERVER['SERVER_SIGNATURE']);

```

`$_SERVER['PATH_TRANSLATED']` 是当前脚本所在文件系统（非文档根目录）的基本路径。这是在服务器进行虚拟到真实路径的映像后的结果。

```php
<?php

var_dump($_SERVER['PATH_TRANSLATED']);

```

`$_SERVER['SCRIPT_NAME']` 是包含当前脚本的路径。这在页面需要指向自己时非常有用。

```php
<?php

var_dump($_SERVER['SCRIPT_NAME']);

```

`$_SERVER['REQUEST_URI']` 是用来指定要访问的页面。

```php
<?php

var_dump($_SERVER['REQUEST_URI']);

```

`$_SERVER['PHP_AUTH_DIGEST']` 是当作为 Apache 模块运行时，进行 HTTP Digest 认证的过程中，此变量被设置成客户端发送的请求头中 Authorization 项的内容（以便作进一步的认证操作）。

```php
<?php

var_dump($_SERVER['PHP_AUTH_DIGEST']);

```

`$_SERVER['PHP_AUTH_USER']` 是当 PHP 运行在 Apache 或 IIS 模块方式下，并且正在使用 HTTP 认证功能，这个变量便是用户输入的用户名。

```php
<?php

var_dump($_SERVER['PHP_AUTH_USER']);

```

`$_SERVER['PHP_AUTH_PW']` 是当 PHP 运行在 Apache 或 IIS 模块方式下，并且正在使用 HTTP 认证功能，这个变量便是用户输入的密码。

```php
<?php

var_dump($_SERVER['PHP_AUTH_PW']);

```

`$_SERVER['AUTH_TYPE']` 是当 PHP 运行在 Apache 模块方式下，并且正在使用 HTTP 认证功能，这个变量便是认证的类型。

```php
<?php

var_dump($_SERVER['AUTH_TYPE']);

```

`$_SERVER['PATH_INFO']` 包含由客户端提供的，跟在真实脚本名称之后并且在查询字符串之前的路径信息，如果存在的话。例如，如果当前脚本是通过 [http://localhost/index.php/foo/bar?foo=foo](http://localhost/index.php/foo/bar?foo=foo) 被访问，那么 `$_SERVER['PATH_INFO']` 将包含 `/foo/bar` 。

```php
<?php

var_dump($_SERVER['PATH_INFO']);

```

`$_SERVER['ORIG_PATH_INFO']` 是在被 PHP 处理之前， `$_SERVER['PATH_INFO']` 的原始版本。

```php
<?php

var_dump($_SERVER['ORIG_PATH_INFO']);

```