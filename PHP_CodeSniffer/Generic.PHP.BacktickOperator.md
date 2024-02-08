Pattern: Use of backtick operator

Issue: -

## Description

Disallows the use of the backtick operator for execution of shell commands. Use of this operator is identical to `shell_exec()`.

These functions are susceptible to Shell Injection attacks. Depending on your configuration, shell script injection can cause your application settings and configuration to leak, or your whole server to be hijacked.

Avoid passing tainted input to these functions - that is input somehow manipulated by the user - unless you're absolutely sure there's no way for it to be dangerous (which you never are without whitelisting).


## Further Reading

* [OWASP - PHP Security Cheat Sheet](https://www.owasp.org/index.php/PHP_Security_Cheat_Sheet#Shell_Injection)
* [PHP_CodeSniffer - Generic.PHP.BacktickOperator](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/PHP/BacktickOperatorSniff.php)