Pattern: Use of deprecated function

Issue: -

## Description

Deprecated APIs should be avoided, and usage updated.

## Examples

Example of **incorrect** code:

```php
$original_plaintext = mcrypt_decrypt("rijndael-128", $key, $ciphertext, MCRYPT_MODE_CBC, $iv)
```

Example of possible **correct** code:

```php
$original_plaintext = openssl_decrypt($ciphertext, "aes-128-gcm", $key, $options=0, $iv, $tag);
```

## Further Reading

* [Deprecated features in PHP 7.1.x](http://php.net/manual/en/migration71.deprecated.php#migration71.deprecated.ext-mcrypt)
* [Deprecated features in PHP 7.0.x](http://php.net/manual/en/migration70.deprecated.php)
* [Deprecated features in PHP 5.6.x](http://php.net/manual/en/migration56.deprecated.php)
* [PHP Manual - Appendices](http://php.net/manual/en/appendices.php)
* [PHP_CodeSniffer - Generic.PHP.DeprecatedFunctions](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/PHP/DeprecatedFunctionsSniff.php)