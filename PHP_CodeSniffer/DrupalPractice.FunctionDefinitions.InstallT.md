Pattern: Use of `t()`/`st()` in `hook_install()`/`hook_requirements()`

Issue: -

## Description

Checks that `t()` and `st()` are not used in `hook_install()` and `hook_requirements()`. Use `$t = get_t()` to retrieve the appropriate localization function name.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.FunctionDefinitions.InstallT](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/FunctionDefinitions/InstallTSniff.php)