Pattern: Missing use of `$form_state['values']`

Issue: -

## Description

Throws a message whenever `$form_state['input']` is used. `$form_state['values']` is preferred.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.General.FormStateInput](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/General/FormStateInputSniff.php)