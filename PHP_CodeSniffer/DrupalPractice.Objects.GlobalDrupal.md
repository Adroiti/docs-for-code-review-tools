Pattern: Missing use of DI for Drupal call

Issue: -

## Description

Checks that `Drupal::service()` and friends is not used in forms, controllers, services.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.Objects.GlobalDrupal](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/Objects/GlobalDrupalSniff.php)