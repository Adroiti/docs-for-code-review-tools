Pattern: Use of top level return with argument

Issue: -

## Description

This rule checks for top level return with arguments. If there is a
top-level return statement with an argument, then the argument is
always ignored. This is detected automatically since Ruby 2.7.

## Examples

```ruby
# Detected since Ruby 2.7
return 1 # 1 is always ignored.
```

## Further Reading

* [RuboCop - Lint/TopLevelReturnWithArgument](https://docs.rubocop.org/rubocop/cops_lint.html#linttoplevelreturnwithargument)
