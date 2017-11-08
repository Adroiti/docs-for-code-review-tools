Pattern: Use of `eval()`

Issue: -

## Description

Used when you use the `eval()` function, to discourage its usage. It's usage may have negative readability, performance and security implications, especially if you accept strings from untrusted or unknown sources.

PHP has features that gives possibility to avoid using `eval()` in most cases.

## Further Reading

* [Stack Overflow - What's alternative of eval function?](https://stackoverflow.com/questions/10671602/whats-alternative-of-eval-function)
* [OWASP - PHP Security Cheat Sheet](https://www.owasp.org/index.php/PHP_Security_Cheat_Sheet#Code_Injection)
* [PHP_CodeSniffer - Squiz.PHP.Eval](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/PHP/EvalSniff.php)