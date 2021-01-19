Pattern: Defining hook in module file

Issue: -

## Description

Checks that `hook_disable()`, `hook_enable()`, `hook_install()`, `hook_uninstall()`,
`hook_requirements()` and `hook_schema()` are not defined in the module file.

## Further Reading

* [PHP_CodeSniffer - Drupal.Semantics.InstallHooks](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/Drupal/Sniffs/Semantics/InstallHooksSniff.php)