Pattern: Disabled `$strictConfigSchema`

Issue: -

## Description

Checks that `$strictConfigSchema` is not set to FALSE in test classes. 

Do not disable strict config schema checking in tests. Instead ensure your module properly declares its schema for configurations.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.Objects.StrictSchemaDisabled](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/Objects/StrictSchemaDisabledSniff.php)