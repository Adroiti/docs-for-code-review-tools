Pattern: Inconsistent access in `hook_menu()`

Issue: -

## Description

Throws a warning if the "access administration pages" string is found in `hook_menu()`.

The administration menu callback should probably use "administer site configuration" - which implies the user can change something - rather than "access administration pages" which is about viewing but not changing configurations.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.General.AccessAdminPages](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/General/AccessAdminPagesSniff.php)