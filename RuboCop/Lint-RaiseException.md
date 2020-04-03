Pattern: Missing use of `StandardError` over `Exception`

Issue: -

## Description

This rule checks for `raise` or `fail` statements which are
raising `Exception` class.

## Examples

```ruby
# bad
raise Exception, 'Error message here'

# good
raise StandardError, 'Error message here'
```

## Further Reading

* [RuboCop - Lint/RaiseException](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintraiseexception)
* [https://rubystyle.guide#raise-exception](https://rubystyle.guide#raise-exception)
