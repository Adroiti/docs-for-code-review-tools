Pattern: Deprecated class method call

Issue: -

## Description

This rule checks for uses of the deprecated class method usages.

## Examples

```ruby
# bad

File.exists?(some_path)
```
```ruby
# good

File.exist?(some_path)
```

## Further Reading

* [RuboCop - Lint/DeprecatedClassMethods](https://docs.rubocop.org/rubocop/cops_lint.html#lintdeprecatedclassmethods)
