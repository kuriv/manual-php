# PDO

* [PDO](#pdo)
  * [PDO::__construct - 创建一个表示数据库连接的 PDO 实例](#pdoconstruct)
  * [PDO::beginTransaction - 开启一个事务](#pdobegintransaction)
  * [PDO::commit - 提交一个事务](#pdocommit)
  * [PDO::errorCode - 获取跟数据库句柄上一次操作相关的 SQLSTATE](#pdoerrorcode)
  * [PDO::errorInfo - 获取与跟据库句柄上一次操作相关的扩展错误信息](#pdoerrorinfo)
  * [PDO::exec - 执行 SQL 语句，并返回受影响的行数](#pdoexec)
  * [PDO::getAttribute - 取回一个数据库连接的属性](#pdogetattribute)
  * [PDO::getAvailableDrivers - 返回一个可用驱动的数组](#pdogetavailabledrivers)
  * [PDO::inTransaction - 检查是否在一个事务内](#pdointransaction)
  * [PDO::lastInsertId - 返回最后插入行的 ID 或序列值](#pdolastinsertid)
  * [PDO::prepare - 准备要执行的语句，并返回语句对象](#pdoprepare)
  * [PDO::query - 执行 SQL 语句，以 PDOStatement 对象形式返回结果集](#pdoquery)
  * [PDO::quote - 为 SQL 查询里的字符串添加引号](#pdoquote)
  * [PDO::rollBack - 回滚一个事务](#pdorollback)
  * [PDO::setAttribute - 设置属性](#pdosetattribute)
* [PDOStatement](#pdostatement)
  * [PDOStatement::bindColumn - 绑定一列到一个 PHP 变量](#pdostatementbindcolumn)
  * [PDOStatement::bindParam - 绑定一个参数到指定的变量名](#pdostatementbindparam)
  * [PDOStatement::bindValue - 把一个值绑定到一个参数](#pdostatementbindvalue)
  * [PDOStatement::closeCursor - 关闭游标，使语句能再次被执行](#pdostatementclosecursor)
  * [PDOStatement::columnCount - 返回结果集中的列数](#pdostatementcolumncount)
  * [PDOStatement::debugDumpParams - 打印一条 SQL 预处理命令](#pdostatementdebugdumpparams)
  * [PDOStatement::errorCode - 获取跟上一次语句句柄操作相关的 SQLSTATE](#pdostatementerrorcode)
  * [PDOStatement::errorInfo - 获取跟上一次语句句柄操作相关的扩展错误信息](#pdostatementerrorinfo)
  * [PDOStatement::execute - 执行一条预处理语句](#pdostatementexecute)
  * [PDOStatement::fetch - 从结果集中获取下一行](#pdostatementfetch)
  * [PDOStatement::fetchAll - 返回一个包含结果集中所有行的数组](#pdostatementfetchall)
  * [PDOStatement::fetchColumn - 从结果集中的下一行返回单独的一列](#pdostatementfetchcolumn)
  * [PDOStatement::fetchObject - 获取下一行并作为一个对象返回](#pdostatementfetchobject)
  * [PDOStatement::getColumnMeta - 返回结果集中一列的元数据](#pdostatementgetcolumnmeta)
  * [PDOStatement::nextRowset - 在一个多行集语句句柄中推进到下一个行集](#pdostatementnextrowset)
  * [PDOStatement::rowCount - 返回受上一个 SQL 语句影响的行数](#pdostatementrowcount)
  * [PDOStatement::setFetchMode - 为语句设置默认的获取模式](#pdostatementsetfetchmode)

## PDO

### PDO::__construct

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

```

### PDO::beginTransaction

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

var_dump($dbh->beginTransaction()); // bool(true)

```

### PDO::commit

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$dbh->beginTransaction();
$dbh->exec("UPDATE users SET name = 'Jerry' WHERE id = 1");
var_dump($dbh->commit()); // bool(true)

```

### PDO::errorCode

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

var_dump($dbh->errorCode());

```

### PDO::errorInfo

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

var_dump($dbh->errorInfo());

```

### PDO::exec

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

var_dump($dbh->exec("UPDATE users SET name = 'Jerry' WHERE id = 1")); // int(1)

```

### PDO::getAttribute

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

var_dump($dbh->getAttribute(PDO::ATTR_AUTOCOMMIT));
var_dump($dbh->getAttribute(PDO::ATTR_CASE));
var_dump($dbh->getAttribute(PDO::ATTR_CLIENT_VERSION));

```

### PDO::getAvailableDrivers

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

var_dump(PDO::getAvailableDrivers());
var_dump($dbh->getAvailableDrivers());

```

### PDO::inTransaction

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

var_dump($dbh->inTransaction()); // bool(false)

$dbh->beginTransaction();
var_dump($dbh->inTransaction()); // bool(true)

```

### PDO::lastInsertId

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

var_dump($dbh->lastInsertId());

```

### PDO::prepare

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

var_dump($dbh->prepare("SELECT * FROM users WHERE id = :id")); // object(PDOStatement)#2 (1) { ["queryString"]=> string(34) "SELECT * FROM users WHERE id = :id" }
var_dump($dbh->prepare("SELECT * FROM users WHERE id = ?"));   // object(PDOStatement)#2 (1) { ["queryString"]=> string(32) "SELECT * FROM users WHERE id = ?" }

```

### PDO::query

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

var_dump($dbh->query("SELECT * FROM users")); // object(PDOStatement)#2 (1) { ["queryString"]=> string(19) "SELECT * FROM users" }

foreach ($dbh->query("SELECT * FROM users") as $row) {
    var_dump($row['id'], $row['name']);
}

```

### PDO::quote

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$string = 'foo';
var_dump($dbh->quote($string)); // string(5) "'foo'"

```

### PDO::rollBack

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$dbh->beginTransaction();
$dbh->exec("UPDATE users SET name = 'Jerry' WHERE id = 1");
var_dump($dbh->rollBack()); // bool(true)

```

### PDO::setAttribute

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

var_dump($dbh->setAttribute(PDO::ATTR_CASE, PDO::CASE_LOWER)); // bool(true)
var_dump($dbh->setAttribute(PDO::ATTR_CASE, PDO::CASE_UPPER)); // bool(true)

```

## PDOStatement

### PDOStatement::bindColumn

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users");
$sth->execute();
var_dump($sth->bindColumn('id', $id));     // bool(true)
var_dump($sth->bindColumn('name', $name)); // bool(true)

while ($sth->fetch()) {
    var_dump(sprintf('#%d %s', $id, $name));
}

```

### PDOStatement::bindParam

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users WHERE id = :id AND name = :name");
$id = 1;
$name = 'Tom';
var_dump($sth->bindParam(':id', $id, PDO::PARAM_INT));     // bool(true)
var_dump($sth->bindParam(':name', $name, PDO::PARAM_STR)); // bool(true)
$sth->execute();
var_dump($sth->fetchAll());

$sth = $dbh->prepare("SELECT * FROM users WHERE id = ? AND name = ?");
$id = 1;
$name = 'Tom';
var_dump($sth->bindParam(1, $id, PDO::PARAM_INT));         // bool(true)
var_dump($sth->bindParam(2, $name, PDO::PARAM_STR));       // bool(true)
$sth->execute();
var_dump($sth->fetchAll());

```

### PDOStatement::bindValue

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users WHERE id = :id AND name = :name");
var_dump($sth->bindValue(':id', 1, PDO::PARAM_INT));       // bool(true)
var_dump($sth->bindValue(':name', 'Tom', PDO::PARAM_STR)); // bool(true)
$sth->execute();
var_dump($sth->fetchAll());

$sth = $dbh->prepare("SELECT * FROM users WHERE id = ? AND name = ?");
var_dump($sth->bindValue(1, 1, PDO::PARAM_INT));           // bool(true)
var_dump($sth->bindValue(2, 'Tom', PDO::PARAM_STR));       // bool(true)
$sth->execute();
var_dump($sth->fetchAll());

```

### PDOStatement::closeCursor

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users");
$sth->execute();
$sth->fetch();
var_dump($sth->closeCursor()); // bool(true)

```

### PDOStatement::columnCount

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users");
$sth->execute();
var_dump($sth->columnCount());

```

### PDOStatement::debugDumpParams

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users WHERE id = :id AND name = :name");
$sth->bindValue(':id', 1, PDO::PARAM_INT);
$sth->bindValue(':name', 'Tom', PDO::PARAM_STR);
$sth->execute();
var_dump($sth->debugDumpParams());

```

### PDOStatement::errorCode

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users");
$sth->execute();
var_dump($sth->errorCode()); // string(5) "00000"

```

### PDOStatement::errorInfo

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users");
$sth->execute();
var_dump($sth->errorInfo()); // array(3) { [0]=> string(5) "00000" [1]=> NULL [2]=> NULL }

```

### PDOStatement::execute

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users WHERE id = :id AND name = :name");
$sth->bindValue(':id', 1, PDO::PARAM_INT);
$sth->bindValue(':name', 'Tom', PDO::PARAM_STR);
var_dump($sth->execute());                               // bool(true)
var_dump($sth->fetchAll());

$sth = $dbh->prepare("SELECT * FROM users WHERE id = :id AND name = :name");
var_dump($sth->execute([':id' => 1, ':name' => 'Tom'])); // bool(true)
var_dump($sth->fetchAll());

$sth = $dbh->prepare("SELECT * FROM users WHERE id = ? AND name = ?");
$sth->bindValue(1, 1, PDO::PARAM_INT);
$sth->bindValue(2, 'Tom', PDO::PARAM_STR);
var_dump($sth->execute());                               // bool(true)
var_dump($sth->fetchAll());

$sth = $dbh->prepare("SELECT * FROM users WHERE id = ? AND name = ?");
var_dump($sth->execute([1, 'Tom']));                     // bool(true)
var_dump($sth->fetchAll());

```

### PDOStatement::fetch

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users");
$sth->execute();
var_dump($sth->fetch());

$sth->execute();
var_dump($sth->fetch(PDO::FETCH_ASSOC));

$sth->execute();
var_dump($sth->fetch(PDO::FETCH_OBJ));

```

### PDOStatement::fetchAll

```php
<?php

class Foo
{
    //
}

/**
 * Return formatted string.
 *
 * @param  int    $id
 * @param  string $name
 * @return string
 */
function foo(int $id, string $name): string
{
    return sprintf('#%d %s', $id, $name);
}

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users");
$sth->execute();
var_dump($sth->fetchAll());

$sth->execute();
var_dump($sth->fetchAll(PDO::FETCH_ASSOC));

$sth->execute();
var_dump($sth->fetchAll(PDO::FETCH_COLUMN, 1));

$sth->execute();
var_dump($sth->fetchAll(PDO::FETCH_COLUMN | PDO::FETCH_GROUP));

$sth->execute();
var_dump($sth->fetchAll(PDO::FETCH_CLASS, 'Foo'));

$sth->execute();
var_dump($sth->fetchAll(PDO::FETCH_FUNC, 'foo'));

```

### PDOStatement::fetchColumn

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users");
$sth->execute();
var_dump($sth->fetchColumn());
var_dump($sth->fetchColumn(1));

```

### PDOStatement::fetchObject

```php
<?php

class Foo
{
    //
}

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users");
$sth->execute();
var_dump($sth->fetchObject());
var_dump($sth->fetchObject('Foo'));

```

### PDOStatement::getColumnMeta

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users");
$sth->execute();
var_dump($sth->getColumnMeta(0));
var_dump($sth->getColumnMeta(1));

```

### PDOStatement::nextRowset

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users");
$sth->execute();
var_dump($sth->fetch());
var_dump($sth->nextRowset());
var_dump($sth->fetch());

```

### PDOStatement::rowCount

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("UPDATE users SET name = :name WHERE id = :id");
$sth->bindValue(':name', 'Jerry', PDO::PARAM_STR);
$sth->bindValue(':id', 1, PDO::PARAM_INT);
$sth->execute();
var_dump($sth->rowCount()); // int(1)

```

### PDOStatement::setFetchMode

```php
<?php

try {
    $dbh = new PDO('mysql:host=127.0.0.1;port=3306;dbname=test', 'root', 'root');
} catch (PDOException $e) {
    echo $e->getMessage();
}

$sth = $dbh->prepare("SELECT * FROM users");
$sth->execute();
var_dump($sth->setFetchMode(PDO::FETCH_ASSOC)); // bool(true)
var_dump($sth->fetchAll());

```