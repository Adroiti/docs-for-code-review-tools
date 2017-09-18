Pattern: Use of `::` for method call

Issue: -

## Description

This rule checks for methods invoked via the `::` operator instead of the `.` operator.

## Examples

```ruby
# bad
FileUtils::rmdir

# good
FileUtils.rmdir
```

## Further Reading

* [RuboCop - Style/ColonMethodCall](https://rubocop.readthedocs.io/en/latest/cops_style/#stylecolonmethodcall)
* [https://github.com/bbatsov/ruby-style-guide#double-colons](https://github.com/bbatsov/ruby-style-guide#double-colons)
