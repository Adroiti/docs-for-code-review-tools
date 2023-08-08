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

* [RuboCop - Style/ColonMethodCall](https://docs.rubocop.org/rubocop/cops_style.html#stylecolonmethodcall)
* [https://github.com/bbatsov/ruby-style-guide#double-colons](https://github.com/bbatsov/ruby-style-guide#double-colons)
