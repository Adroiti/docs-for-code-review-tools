Pattern: Use of assignment in condition

Issue: -

## Description

Detects variable assignments being made within conditions. This is a typical code smell and more often than not a comparison was intended.

Note: this rule does not detect variable assignments in ternaries without parentheses!

## Further Reading

* [WordPress.CodeAnalysis.AssignmentInCondition](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/CodeAnalysis/AssignmentInConditionSniff.php)