Pattern: Use of `eval()` to create object

Issue: -

## Description

Ensures that `eval()` is not used to create objects. PHP has features that gives possibility to avoid using `eval()` in most cases.

## Further Reading

* [Stack Overflow - What's alternative of eval function?](https://stackoverflow.com/questions/10671602/whats-alternative-of-eval-function)
* [OWASP - PHP Security Cheat Sheet](https://www.owasp.org/index.php/PHP_Security_Cheat_Sheet#Code_Injection)
* [PHP_CodeSniffer - MySource.PHP.EvalObjectFactory](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/MySource/Sniffs/PHP/EvalObjectFactorySniff.php)