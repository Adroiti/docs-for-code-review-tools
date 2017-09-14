Pattern: Use of `::` for method call

Issue: -

## Description

This cop checks for methods invoked via the `::` operator instead of the `.` operator.

### Example

```ruby
# bad
FileUtils::rmdir

# good
FileUtils.rmdir
```

## Further Reading

* [RuboCop - Style/ColonMethodCall](https://rubocop.readthedocs.io/en/latest/cops_style/#stylecolonmethodcall)
* [https://github.com/bbatsov/ruby-style-guide#double-colons](https://github.com/bbatsov/ruby-style-guide#double-colons)
