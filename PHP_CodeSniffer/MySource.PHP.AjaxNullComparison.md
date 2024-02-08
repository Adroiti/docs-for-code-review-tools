Pattern: Null comparison for Ajax request

Issue: -

## Description

Ensures that values submitted via JS are not compared to `NULL`.

With jQuery 1.8, the behavior of Ajax requests changed so that null values are submitted as null= instead of null=null.

## Further Reading

* [PHP_CodeSniffer - MySource.PHP.AjaxNullComparison](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/MySource/Sniffs/PHP/AjaxNullComparisonSniff.php)