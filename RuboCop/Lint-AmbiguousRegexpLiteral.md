Pattern: Ambiguous RegExp literal

Issue: -

## Description

This cop checks for ambiguous RegExp literals in the first argument of a method invocation without parentheses.

### Example

```ruby
# bad

# This is interpreted as a method invocation with a RegExp literal,
# but it could possibly be `/` method invocations.
# (i.e. `do_something./(pattern)./(i)`)
do_something /pattern/i
```
```ruby
# good

# With parentheses, there's no ambiguity.
do_something(/pattern/i)
```

## Further Reading

* [RuboCop - Lint/AmbiguousRegexpLiteral](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintambiguousregexpliteral)
