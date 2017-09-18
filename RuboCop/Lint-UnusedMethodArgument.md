Pattern: Unused method argument

Issue: -

## Description

Use `_` to prefix unused block parameters and local variables. It's also acceptable to use just `_` (although it's a bit less descriptive). This convention is recognized by the Ruby interpreter and tools like RuboCop and will suppress their unused variable warnings.

## Examples

```ruby
# bad

def some_method(used, unused, _unused_but_allowed)
  puts used
end
```
```ruby
# good

def some_method(used, _unused, _unused_but_allowed)
  puts used
end
```

## Default configuration

Attribute | Value
--- | ---
AllowUnusedKeywordArguments | false
IgnoreEmptyMethods | true

## Further Reading

* [RuboCop - Lint/UnusedMethodArgument](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintunusedmethodargument)
* [https://github.com/bbatsov/ruby-style-guide#underscore-unused-vars](https://github.com/bbatsov/ruby-style-guide#underscore-unused-vars)
