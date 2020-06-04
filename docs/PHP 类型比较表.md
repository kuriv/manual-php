# PHP 类型比较表

* [使用函数](#使用函数)
* [使用松散比较](#使用松散比较)
* [使用严格比较](#使用严格比较)

## 使用函数

| 表达式            | gettype() | empty() | is_null() | isset() | if ($x) |
| ----------------- | --------- | ------- | --------- | ------- | ------- |
| **$x = '';**      | string    | true    | false     | true    | false   |
| **$x = null;**    | NULL      | true    | true      | false   | false   |
| **$x;**           | NULL      | true    | true      | false   | false   |
| **unset($x);**    | NULL      | true    | true      | false   | false   |
| **$x = [];**      | array     | true    | false     | true    | false   |
| **$x = false;**   | boolean   | true    | false     | true    | false   |
| **$x = true;**    | boolean   | false   | false     | true    | true    |
| **$x = 1;**       | integer   | false   | false     | true    | true    |
| **$x = 42;**      | integer   | false   | false     | true    | true    |
| **$x = 0;**       | integer   | true    | false     | true    | false   |
| **$x = -1;**      | integer   | false   | false     | true    | true    |
| **$x = '1';**     | string    | false   | false     | true    | true    |
| **$x = '0';**     | string    | true    | false     | true    | false   |
| **$x = '-1';**    | string    | false   | false     | true    | true    |
| **$x = 'php';**   | string    | false   | false     | true    | true    |
| **$x = 'true';**  | string    | false   | false     | true    | true    |
| **$x = 'false';** | string    | false   | false     | true    | true    |

## 使用松散比较

|           | true  | false | 1     | 0     | -1    | '1'   | '0'   | '-1'  | NULL  | []    | 'php' | ''    |
| --------- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| **true**  | true  | false | true  | false | true  | true  | false | true  | false | false | true  | false |
| **false** | false | true  | false | true  | false | false | true  | false | true  | true  | false | true  |
| **1**     | true  | false | true  | false | false | true  | false | false | false | false | false | false |
| **0**     | false | true  | false | true  | false | false | true  | false | true  | false | true  | true  |
| **-1**    | true  | false | false | false | true  | false | false | true  | false | false | false | false |
| **'1'**   | true  | false | true  | false | false | true  | false | false | false | false | false | false |
| **'0'**   | false | true  | false | true  | false | false | true  | false | false | false | false | false |
| **'-1'**  | true  | false | false | false | true  | false | false | true  | false | false | false | false |
| **NULL**  | false | true  | false | true  | false | false | false | false | true  | true  | false | true  |
| **[]**    | false | true  | false | false | false | false | false | false | true  | true  | false | false |
| **'php'** | true  | false | false | true  | false | false | false | false | false | false | true  | false |
| **''**    | false | true  | false | true  | false | false | false | false | true  | false | false | true  |

## 使用严格比较

|           | true  | false | 1     | 0     | -1    | '1'   | '0'   | '-1'  | NULL  | []    | 'php' | ''    |
| --------- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| **true**  | true  | false | false | false | false | false | false | false | false | false | false | false |
| **false** | false | true  | false | false | false | false | false | false | false | false | false | false |
| **1**     | false | false | true  | false | false | false | false | false | false | false | false | false |
| **0**     | false | false | false | true  | false | false | false | false | false | false | false | false |
| **-1**    | false | false | false | false | true  | false | false | false | false | false | false | false |
| **'1'**   | false | false | false | false | false | true  | false | false | false | false | false | false |
| **'0'**   | false | false | false | false | false | false | true  | false | false | false | false | false |
| **'-1'**  | false | false | false | false | false | false | false | true  | false | false | false | false |
| **NULL**  | false | false | false | false | false | false | false | false | true  | false | false | false |
| **[]**    | false | false | false | false | false | false | false | false | false | true  | false | false |
| **'php'** | false | false | false | false | false | false | false | false | false | false | true  | false |
| **''**    | false | false | false | false | false | false | false | false | false | false | false | true  |
