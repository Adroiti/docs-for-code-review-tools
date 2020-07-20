Pattern: Missing use of `<=`

Issue: -

## Description

Identifies usages of `ancestors.include?` and suggests to use `<=` instead.

## Examples

```ruby
# bad
A.ancestors.include?(B)

# good
A <= B
```

## Further Reading

* [RuboCop - Performance/AncestorsInclude](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performanceancestorsinclude)