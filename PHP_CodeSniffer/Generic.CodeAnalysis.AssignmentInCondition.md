Pattern: Assignment in condition

Issue: -

## Description

Detects variable assignments being made within conditions.

This is a typical code smell and more often than not a comparison was intended.

Note: this rule does not detect variable assignments in the conditional part of ternaries!

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.AssignmentInCondition](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/AssignmentInConditionSniff.php)