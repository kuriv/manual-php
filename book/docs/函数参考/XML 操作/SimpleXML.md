# SimpleXML

* [SimpleXMLElement](#simplexmlelement)
  * [SimpleXMLElement::__construct - 创建一个新的 SimpleXMLElement 对象](#simplexmlelementconstruct)
  * [SimpleXMLElement::addAttribute - 给 SimpleXMLElement 对象添加属性](#simplexmlelementaddattribute)
  * [SimpleXMLElement::addChild - 将子元素添加到 XML 节点](#simplexmlelementaddchild)
  * [SimpleXMLElement::asXML - 返回基于 SimpleXMLElement 对象的格式正确的 XML 字符串](#simplexmlelementasxml)
  * [SimpleXMLElement::attributes - 标识元素的属性](#simplexmlelementattributes)
  * [SimpleXMLElement::children - 查找指定节点的子代](#simplexmlelementchildren)
  * [SimpleXMLElement::count - 统计元素的子代数量](#simplexmlelementcount)
  * [SimpleXMLElement::getDocNamespaces - 返回文档中声明的名称空间](#simplexmlelementgetdocnamespaces)
  * [SimpleXMLElement::getName - 获取 XML 元素的名称](#simplexmlelementgetname)
  * [SimpleXMLElement::getNamespaces - 返回文档中使用的名称空间](#simplexmlelementgetnamespaces)
  * [SimpleXMLElement::registerXPathNamespace - 为下一个 XPath 查询创建一个前缀 / 命名空间下文](#simplexmlelementregisterxpathnamespace)
  * [SimpleXMLElement::saveXML - 返回基于 SimpleXMLElement 对象的格式正确的 XML 字符串](#simplexmlelementsavexml)
  * [SimpleXMLElement::__toString - 返回字符串内容](#simplexmlelementtostring)
  * [SimpleXMLElement::xpath - 对 XML 数据进行 XPath 查询](#simplexmlelementxpath)
* [SimpleXMLIterator](#simplexmliterator)
  * s
* [SimpleXML](#simplexml)
  * [simplexml_import_dom - 从 DOM 节点获取 SimpleXMLElement 对象](#simplexmlimportdom)
  * [simplexml_load_file - 将 XML 文件解析为对象](#simplexmlloadfile)
  * [simplexml_load_string - 将 XML 字符串解析为对象](#simplexmlloadstring)

## SimpleXMLElement

### SimpleXMLElement::__construct

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
              <body>Here is some text.</body>
          </document>
          XML;
var_dump(new SimpleXMLElement($xml)); // object(SimpleXMLElement)#1 (2) { ["title"]=> string(3) "XML" ["body"]=> string(18) "Here is some text." }

```

### SimpleXMLElement::addAttribute 

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
              <body>Here is some text.</body>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
$xml->addAttribute('foo', 'bar');
var_dump($xml); // object(SimpleXMLElement)#1 (3) { ["@attributes"]=> array(1) { ["foo"]=> string(3) "bar" } ["title"]=> string(3) "XML" ["body"]=> string(18) "Here is some text." }

```

### SimpleXMLElement::addChild

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
var_dump($xml->addChild('body', 'Here is some text.')); // object(SimpleXMLElement)#2 (1) { [0]=> string(18) "Here is some text." }
var_dump($xml);                                         // object(SimpleXMLElement)#1 (2) { ["title"]=> string(3) "XML" ["body"]=> string(18) "Here is some text." }

```

### SimpleXMLElement::asXML

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
              <body>Here is some text.</body>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
echo $xml->asXML();

```

### SimpleXMLElement::attributes

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document foo="bar">
              <title>XML</title>
              <body>Here is some text.</body>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
var_dump($xml->attributes()); // object(SimpleXMLElement)#2 (1) { ["@attributes"]=> array(1) { ["foo"]=> string(3) "bar" } }

```

### SimpleXMLElement::children

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
              <body>
                  <p>Here is some text.</p>
              </body>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
var_dump($xml->children());                   // object(SimpleXMLElement)#2 (2) { ["title"]=> string(3) "XML" ["body"]=> object(SimpleXMLElement)#4 (1) { ["p"]=> string(18) "Here is some text." } }
var_dump($xml->children()->body->children()); // object(SimpleXMLElement)#4 (1) { ["p"]=> string(18) "Here is some text." }

```

### SimpleXMLElement::count

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
              <body>
                  <p>Here is some text.</p>
              </body>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
var_dump($xml->count()); // int(2)

```

### SimpleXMLElement::getDocNamespaces

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document xmlns:title="http://www.example.com/title" xmlns:body="http://www.example.com/body" xmlns:p="http://www.example.com/p">
              <title>XML</title>
              <body>
                  <p>Here is some text.</p>
              </body>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
var_dump($xml->getDocNamespaces()); // array(3) { ["title"]=> string(28) "http://www.example.com/title" ["body"]=> string(27) "http://www.example.com/body" ["p"]=> string(24) "http://www.example.com/p" }

```

### SimpleXMLElement::getName

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
              <body>
                  <p>Here is some text.</p>
              </body>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
foreach ($xml->children() as $children) {
    var_dump($children->getName());
}
// string(5) "title"
// string(4) "body"

```

### SimpleXMLElement::getNamespaces

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document xmlns:title="http://www.example.com/title" xmlns:body="http://www.example.com/body" xmlns:p="http://www.example.com/p">
              <title:title>XML</title:title>
              <body:body>
                  <p>Here is some text.</p>
              </body:body>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
var_dump($xml->getNamespaces(true)); // array(2) { ["title"]=> string(28) "http://www.example.com/title" ["body"]=> string(27) "http://www.example.com/body" }

```

### SimpleXMLElement::registerXPathNamespace

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document xmlns:title="http://www.example.com/title">
              <title:title>XML</title:title>
              <body>
                  <p>Here is some text.</p>
              </body>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
$xml->registerXPathNamespace('title', 'http://www.example.com/title');
var_dump($xml->xpath('//title:title')); // array(1) { [0]=> object(SimpleXMLElement)#2 (1) { [0]=> string(3) "XML" } }

```

### SimpleXMLElement::saveXML

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
              <body>Here is some text.</body>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
echo $xml->saveXML();

```

### SimpleXMLElement::__toString

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
              <body>
                  <p>Here is some text.</p>
              </body>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
echo $xml;
print $xml;

```

### SimpleXMLElement::xpath

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
              <body>
                  <p>Here is some text.</p>
              </body>
          </document>
          XML;
$xml = new SimpleXMLElement($xml);
var_dump($xml->xpath('/document/body')); // array(1) { [0]=> object(SimpleXMLElement)#2 (1) { ["p"]=> string(18) "Here is some text." } }

```

## SimpleXMLIterator





## SimpleXML

### simplexml_import_dom

```php
<?php

$dom = new DomDocument;
$dom->loadXML('<document><title>XML</title><body>Here is some text.</body></document>');
var_dump(simplexml_import_dom($dom)); // object(SimpleXMLElement)#2 (2) { ["title"]=> string(3) "XML" ["body"]=> string(18) "Here is some text." }

```

### simplexml_load_file

```php
<?php

var_dump(simplexml_load_file(__DIR__ . '/example.xml')); // object(SimpleXMLElement)#1 (2) { ["title"]=> string(3) "XML" ["body"]=> string(18) "Here is some text." }

```

上例中的 `example.xml` 文件内容：

```xml
<?xml version="1.0" encoding="UTF-8"?>
    <document>
        <title>XML</title>
        <body>Here is some text.</body>
</document>
```

### simplexml_load_string

```php
<?php

$xml = <<<XML
          <?xml version="1.0" encoding="UTF-8"?>
          <document>
              <title>XML</title>
              <body>Here is some text.</body>
          </document>
          XML;
var_dump(simplexml_load_string($xml)); // object(SimpleXMLElement)#1 (2) { ["title"]=> string(3) "XML" ["body"]=> string(18) "Here is some text." }

```



