Pattern: Possible incorrect usage of redirection operator

Issue: -

## Description

In many programming languages, the comparison operator for 'greater than' is `>` but `PowerShell` uses `-gt` for it and `-ge` (greater or equal) for `>=`. Therefore it can easily happen that the wrong operator is used unintentionally and this rule catches a few special cases where the likelihood of that is quite high.

The rule looks for usages of `>` or `>=` operators inside `if`, `elseif`, `while` and `do-while` statements because this is likely going to be unintentional usage.

Example of **incorrect** code:

```` PowerShell
if ($a > $b)
{
    ...
}
````

Example of **correct** code:

```` PowerShell
if ($a -gt $b)
{
    ...
}
````

## Further Reading

* [PSScriptAnalyzer - PossibleIncorrectUsageOfRedirectionOperator](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/PossibleIncorrectUsageOfRedirectionOperator.md)