# CURL 上下文选项

```php
<?php

$data = http_build_query([
    'foo' => 'foo',
    'bar' => 'bar'
]);
$option = [
    'http' => [
        'method'  => 'POST',
        'header'  => 'Content-Type: application/x-www-form-urlencoded',
        'content' => $data
    ]
];
$context = stream_context_create($option);
var_dump(file_get_contents('http://www.example.com', false, $context));

```

