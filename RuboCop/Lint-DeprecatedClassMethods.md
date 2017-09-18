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

* [RuboCop - Lint/DeprecatedClassMethods](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintdeprecatedclassmethods)
