Pattern: Use of _console_ name

Issue: -

## Description

Variables, functions and labels must not be named _console_; name may conflict with Firebug internal variable.

## Further Reading

* [PHP_CodeSniffer - MySource.Debug.FirebugConsole](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/MySource/Sniffs/Debug/FirebugConsoleSniff.php)