# 从 HTML 中分离

凡是在一对起始标记和结束标记之外的内容都会被 PHP 解析器忽略，这使得 PHP 文件可以具备混合内容。可以使 PHP 嵌入到 HTML 文档中去。

```php
<!DOCTYPE html>
<html lang="zh-cmn-Hans">
    <head>
        <meta charset="utf-8"/>
    </head>
    <body>
        <p>Hello, World!</p>
        <?php echo 'Hello, World!'; ?>
        <p>Hello, World!</p>
        <?php echo 'Hello, World!'; ?>
    </body>
</html>
```

当处于条件语句中间时，此时 PHP 解释器会根据条件判断来决定哪些输出哪些跳过。 PHP 将跳过条件语句未达成的段落，即使该段落位于 PHP 开始和结束标记之外。由于 PHP 解释器会在条件未达成时直接跳过该段条件语句块，因此 PHP 会根据条件来忽略之。要输出大段文本时，跳出 PHP 解析模式通常比将文本通过 `echo` 或 `print` 输出更有效率。

```php
<?php if (true) : ?>
    <p>Hello, World!</p>
<?php else : ?>
    <p>PHP</p>
<?php endif; ?>
```

