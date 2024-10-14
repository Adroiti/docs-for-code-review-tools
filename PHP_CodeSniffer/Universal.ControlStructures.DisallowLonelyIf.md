Pattern: Use of lonely `if`

Issue: -

## Description

Disallow `if` statements as the only statement in an `else` block.

Note: This rule will not fix the indentation of the "inner" code. It is strongly recommended to run this sniff together with the `Generic.WhiteSpace.ScopeIndent` sniff to get the correct indentation.


## Further Reading

* [Universal.ControlStructures.DisallowLonelyIf](https://github.com/PHPCSStandards/PHPCSExtra?tab=readme-ov-file#universalcontrolstructuresdisallowlonelyif-wrench-books)