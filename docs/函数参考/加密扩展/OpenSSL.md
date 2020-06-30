# OpenSSL

* [openssl_cipher_iv_length - 获取密码 iv 长度](#opensslcipherivlength)
* [openssl_csr_export_to_file - 将 CSR 导出到文件](#opensslcsrexporttofile)
* [openssl_csr_export - 将 CSR 作为字符串导出](#opensslcsrexport)
* [openssl_csr_get_public_key - 返回 CSR 的公钥](#opensslcsrgetpublickey)
* [openssl_csr_get_subject - 返回 CSR 的主题](#opensslcsrgetsubject)
* [openssl_csr_new - 生成一个 CSR](#opensslcsrnew)
* openssl_csr_sign - 用另一个证书签署 CSR（或者本身）并且生成一个证书
* [openssl_decrypt - 解密数据](#openssldecrypt)
* openssl_dh_compute_key - 计算远程 DH 密钥（公钥）和本地 DH 密钥的共享密钥
* [openssl_digest - 计算摘要](#openssldigest)
* [openssl_encrypt - 加密数据](#opensslencrypt)
* [openssl_error_string - 返回 openSSL 错误消息](#opensslerrorstring)
* [openssl_free_key - 释放密钥资源](#opensslfreekey)
* [openssl_get_cert_locations - 检索可用的证书位置](#opensslgetcertlocations)
* [openssl_get_cipher_methods - 获取可用的加密算法](#opensslgetciphermethods)
* [openssl_get_curve_names - 获得 ECC 的可用曲线名称列表](#opensslgetcurvenames)
* [openssl_get_md_methods - 获取可用的摘要算法](#opensslgetmdmethods)
* [openssl_get_privatekey - 获取私钥](#opensslgetprivatekey)
* openssl_get_publickey - 从证书中解析公钥，以供使用
* openssl_open - 打开密封的数据
* [openssl_pbkdf2 - 生成一个 PKCS5 v2 PBKDF2 字符串](#opensslpbkdf2)
* openssl_pkcs12_export_to_file - 输出一个 PKCS#12 兼容的证书存储文件
* openssl_pkcs12_export - 将 PKCS#12 兼容证书存储文件导出到变量
* openssl_pkcs12_read - 将 PKCS#12 证书存储区解析到数组中
* openssl_pkcs7_decrypt - 解密一个 S/MIME 加密的消息
* openssl_pkcs7_encrypt - 加密一个 S/MIME 消息
* openssl_pkcs7_read - 将 PKCS7 文件导出为 PEM 格式证书的数组
* openssl_pkcs7_sign - 对一个 S/MIME 消息进行签名
* openssl_pkcs7_verify - 校验一个已签名的 S/MIME 消息的签名
* [openssl_pkey_export_to_file - 将密钥导出到文件中](#opensslpkeyexporttofile)
* [openssl_pkey_export - 将一个密钥的可输出表示转换为字符串](#opensslpkeyexport)
* [openssl_pkey_free - 释放一个私钥](#opensslpkeyfree)
* [openssl_pkey_get_details - 返回包含密钥详情的数组](#opensslpkeygetdetails)
* [openssl_pkey_get_private - 获取私钥](#opensslpkeygetprivate)
* openssl_pkey_get_public - 从证书中解析公钥，以供使用
* [openssl_pkey_new - 生成一个新的私钥](#opensslpkeynew)
* openssl_private_decrypt - 使用私钥解密数据
* openssl_private_encrypt - 使用私钥加密数据
* openssl_public_decrypt - 使用公钥解密数据
* openssl_public_encrypt - 使用公钥加密数据
* [openssl_random_pseudo_bytes - 生成一个伪随机字节串](#opensslrandompseudobytes)
* openssl_seal - 加密数据
* openssl_sign - 生成签名
* openssl_spki_export_challenge - 导出与签名公钥和挑战相关的挑战字符串
* openssl_spki_export - 通过签名公钥和挑战导出一个可用的 PEM 格式的公钥
* [openssl_spki_new - 生成一个新的签名公钥和挑战](#opensslspkinew)
* openssl_spki_verify - 验证签名公钥和挑战
* openssl_verify - 验证签名
* openssl_x509_check_private_key - 检查私钥是否对应于证书
* openssl_x509_checkpurpose - 验证是否可以为特定目的使用证书
* openssl_x509_export_to_file - 导出证书至文件
* openssl_x509_export - 以字符串格式导出证书
* openssl_x509_fingerprint - 计算一个给定的 x.509 证书的指纹或摘要
* openssl_x509_free - 释放证书资源
* openssl_x509_parse - 解析一个 x.509 证书并作为一个数组返回信息
* openssl_x509_read - 解析一个 x.509 证书并返回一个资源标识符
* openssl_x509_verify - 根据公钥验证 x.509 证书的数字签名

## openssl_cipher_iv_length

```php
<?php

var_dump(openssl_cipher_iv_length('AES-128-CBC')); // int(16)

```

## openssl_csr_export_to_file

```php
<?php

$dn = ['countryName' => 'GB'];
$privkey = openssl_pkey_new();
var_dump(openssl_csr_export_to_file(openssl_csr_new($dn, $privkey), __DIR__ . '/example.pem')); // bool(true)

```

## openssl_csr_export

```php
<?php

$dn = ['countryName' => 'GB'];
$privkey = openssl_pkey_new();
var_dump(openssl_csr_export(openssl_csr_new($dn, $privkey), $out), $out);

```

## openssl_csr_get_public_key

```php
<?php

$dn = ['countryName' => 'GB'];
$privkey = openssl_pkey_new();
var_dump(openssl_csr_get_public_key(openssl_csr_new($dn, $privkey))); // resource(6) of type (OpenSSL key)

```

## openssl_csr_get_subject

```php
<?php

$dn = ['countryName' => 'GB'];
$privkey = openssl_pkey_new();
var_dump(openssl_csr_get_subject(openssl_csr_new($dn, $privkey))); // array(3) { ["C"]=> string(2) "GB" ["ST"]=> string(10) "Some-State" ["O"]=> string(24) "Internet Widgits Pty Ltd" }

```

## openssl_csr_new

```php
<?php

$dn = ['countryName' => 'GB'];
$privkey = openssl_pkey_new();
var_dump(openssl_csr_new($dn, $privkey)); // resource(5) of type (OpenSSL X.509 CSR)

```

## openssl_csr_sign

```php

```

## openssl_decrypt

```php
<?php

$key = openssl_random_pseudo_bytes(4);
$iv = openssl_random_pseudo_bytes(16);
$data = openssl_encrypt('foo', 'AES-128-CBC', $key, 0, $iv);
var_dump(openssl_decrypt($data, 'AES-128-CBC', $key, 0, $iv)); // string(3) "foo"

```

## openssl_dh_compute_key

```php

```

## openssl_digest

```php
<?php

var_dump(openssl_digest('foo', 'md5'));    // string(32) "acbd18db4cc2f85cedef654fccc4a4d8"
var_dump(openssl_digest('foo', 'sha256')); // string(64) "2c26b46b68ffc68ff99b453c1d30413413422d706483bfa0f98a5e886266e7ae"

```

## openssl_encrypt

```php
<?php

$key = openssl_random_pseudo_bytes(4);
$iv = openssl_random_pseudo_bytes(16);
var_dump(openssl_encrypt('foo', 'AES-128-CBC', $key, 0, $iv));

```

## openssl_error_string

```php
<?php

var_dump(openssl_error_string()); // bool(false)

```

## openssl_free_key

```php
<?php

openssl_free_key(openssl_pkey_new());

```

## openssl_get_cert_locations

```php
<?php

var_dump(openssl_get_cert_locations());

```

## openssl_get_cipher_methods

```php
<?php

var_dump(openssl_get_cipher_methods());
var_dump(openssl_get_cipher_methods(true));

```

## openssl_get_curve_names

```php
<?php

var_dump(openssl_get_curve_names());

```

## openssl_get_md_methods

```php
<?php

var_dump(openssl_get_md_methods());
var_dump(openssl_get_md_methods(true));

```

## openssl_get_privatekey

```php
<?php

var_dump(openssl_get_privatekey(openssl_pkey_new())); // resource(4) of type (OpenSSL key)

```

## openssl_get_publickey

```php

```

## openssl_open

```php

```

## openssl_pbkdf2

```php
<?php

var_dump(openssl_pbkdf2('foo', openssl_random_pseudo_bytes(4), 20, 10000));

```

## openssl_pkcs12_export_to_file

```php

```

## openssl_pkcs12_export

```php

```

## openssl_pkcs12_read

```php

```

## openssl_pkcs7_decrypt

```php

```

## openssl_pkcs7_encrypt

```php

```

## openssl_pkcs7_read

```php

```

## openssl_pkcs7_sign

```php

```

## openssl_pkcs7_verify

```php

```

## openssl_pkey_export_to_file

```php
<?php

var_dump(openssl_pkey_export_to_file(openssl_pkey_new(), __DIR__ . '/example.key')); // bool(true)

```

## openssl_pkey_export

```php
<?php

var_dump(openssl_pkey_export(openssl_pkey_new(), $out), $out);

```

## openssl_pkey_free

```php
<?php

openssl_pkey_free(openssl_pkey_new());

```

## openssl_pkey_get_details

```php
<?php

var_dump(openssl_pkey_get_details(openssl_pkey_new()));

```

## openssl_pkey_get_private

```php
<?php

var_dump(openssl_pkey_get_private(openssl_pkey_new())); // resource(4) of type (OpenSSL key)

```

## openssl_pkey_get_public

```php

```

## openssl_pkey_new

```php
<?php

var_dump(openssl_pkey_new()); // resource(4) of type (OpenSSL key)

```

## openssl_private_decrypt

```php

```

## openssl_private_encrypt

```php

```

## openssl_public_decrypt

```php

```

## openssl_public_encrypt

```php

```

## openssl_random_pseudo_bytes

```php
<?php

var_dump(openssl_random_pseudo_bytes(1));
var_dump(openssl_random_pseudo_bytes(2));
var_dump(openssl_random_pseudo_bytes(3));
var_dump(openssl_random_pseudo_bytes(4));
var_dump(openssl_random_pseudo_bytes(4, $crypto_strong), $crypto_strong);

```

## openssl_seal

```php

```

## openssl_sign

```php

```

## openssl_spki_export_challenge

```php

```

## openssl_spki_export

```php

```

## openssl_spki_new

```php
<?php

var_dump(openssl_spki_new(openssl_pkey_new(), 'foo'));

```

## openssl_spki_verify

```php

```

## openssl_verify

```php

```

## openssl_x509_check_private_key

```php

```

## openssl_x509_checkpurpose

```php

```

## openssl_x509_export_to_file

```php

```

## openssl_x509_export

```php

```

## openssl_x509_fingerprint

```php

```

## openssl_x509_free

```php

```

## openssl_x509_parse

```php

```

## openssl_x509_read

```php

```

## openssl_x509_verify

```php

```