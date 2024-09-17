Pattern: Malformed in/decrement in stand-alone statement

Issue: -

## Description

Disallows the use of post-in/decrements in stand-alone statements. Using pre-in/decrement is more in line with the principle of least astonishment and prevents bugs when code gets moved around at a later point in time.

This rule also discourages the use of multiple increment/decrement operators in a stand-alone statement.

## Further Reading

* [Universal.Operators.DisallowStandalonePostIncrementDecrement](https://github.com/PHPCSStandards/PHPCSExtra?tab=readme-ov-file#universaloperatorsdisallowstandalonepostincrementdecrement-wrench-bar_chart-books)