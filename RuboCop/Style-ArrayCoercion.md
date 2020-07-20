Pattern: Missing use of `Array()`

Issue: -

## Description

Enforces the use of `Array()` instead of explicit `Array` check or `[*var]`.

## Examples

```ruby
# bad
paths = [paths] unless paths.is_a?(Array)
paths.each { |path| do_something(path) }

# bad (always creates a new Array instance)
[*paths].each { |path| do_something(path) }

# good (and a bit more readable)
Array(paths).each { |path| do_something(path) }
```

## Further Reading

* [RuboCop - Style/ArrayCoercion](https://docs.rubocop.org/rubocop/cops_style.html#stylearraycoercion)
