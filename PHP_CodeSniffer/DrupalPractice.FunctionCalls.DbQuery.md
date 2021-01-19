Pattern: Use of `UPDATE`/`DELETE` in `db_query()` 

Issue: -

## Description

Checks that `UPDATE`/`DELETE` queries are not used in `db_query()` in Drupal 7.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.FunctionCalls.DbQuery](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/FunctionCalls/DbQuerySniff.php)