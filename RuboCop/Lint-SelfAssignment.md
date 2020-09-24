Pattern: Use of self-assignment

Issue: -

## Description

This rule checks for self-assignments.

## Examples

```ruby
# bad
foo = foo
foo, bar = foo, bar
Foo = Foo

# good
foo = bar
foo, bar = bar, foo
Foo = Bar
```

## Further Reading

* [RuboCop - Lint/SelfAssignment](https://docs.rubocop.org/rubocop/cops_lint.html#lintselfassignment)
