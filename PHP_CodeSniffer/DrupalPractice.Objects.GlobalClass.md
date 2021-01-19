Pattern: Missing use of DI for global class

Issue: -

## Description

Checks that `Node::load()` calls and friends are not used in forms, controllers or
services.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.Objects.GlobalClass](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/Objects/GlobalClassSniff.php)