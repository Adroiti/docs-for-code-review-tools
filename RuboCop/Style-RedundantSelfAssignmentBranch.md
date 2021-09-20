Pattern: Redundant self-assignment branch

Issue: -

## Description

Checks for places where conditional branch makes redundant self-assignment.

It only detects local variable because it may replace state of instance variable, class variable, and global variable that have state across methods with nil.

## Examples

```ruby
# bad
foo = condition ? bar : foo

# good
foo = bar if condition

# bad
foo = condition ? foo : bar

# good
foo = bar unless condition
```

## Further Reading

* [RuboCop - Style/RedundantSelfAssignmentBranch](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantselfassignmentbranch)
