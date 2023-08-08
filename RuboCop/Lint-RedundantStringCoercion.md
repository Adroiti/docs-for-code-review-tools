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

* [RuboCop - Lint/RedundantStringCoercion](https://docs.rubocop.org/rubocop/cops_lint.html#lintredundantstringcoercion)
* [https://github.com/bbatsov/ruby-style-guide#no-to-s](https://github.com/bbatsov/ruby-style-guide#no-to-s)
