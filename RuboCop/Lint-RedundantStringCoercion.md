Pattern: Redundant string coercion

Issue: -

## Description

This rule checks for string conversion in string interpolation, which is redundant.

## Examples

```ruby
# bad

"result is #{something.to_s}"
```
```ruby
# good

"result is #{something}"
```

## Further Reading

* [RuboCop - Lint/RedundantStringCoercion](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintredundantstringcoercion)
* [https://github.com/bbatsov/ruby-style-guide#no-to-s](https://github.com/bbatsov/ruby-style-guide#no-to-s)
