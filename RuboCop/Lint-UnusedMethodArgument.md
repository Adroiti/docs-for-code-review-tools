Pattern: Unused method argument

Issue: -

## Description

This rule checks for unused method arguments.

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
