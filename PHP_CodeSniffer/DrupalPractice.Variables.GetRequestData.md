Pattern: Direct access of super global

Issue: -

## Description

Ensures that Symfony request object is used to access super globals. Inject the `request.stack` service and use `$stack->getCurrentRequest()->%s`.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.Variables.GetRequestData](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/Variables/GetRequestDataSniff.php)