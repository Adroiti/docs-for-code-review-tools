Pattern: Redundant string conversion in interpolation

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

* [RuboCop - Lint/RedundantStringConversionInInterpolation](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintredundantstringconversionininterpolation)
* [https://github.com/bbatsov/ruby-style-guide#no-to-s](https://github.com/bbatsov/ruby-style-guide#no-to-s)
