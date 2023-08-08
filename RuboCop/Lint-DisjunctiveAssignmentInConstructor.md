Pattern: Disjunctive assignment in constructor

Issue: -

## Description

In ruby, an instance variable is `nil` until a value is assigned, so the disjunction is unnecessary. A plain assignment has the same effect.

### Examples

```ruby
# bad
def initialize
  @x ||= 1
end

# good
def initialize
  @x = 1
end
```

## Further Reading

* [RuboCop - Lint/DisjunctiveAssignmentInConstructor](https://docs.rubocop.org/rubocop/cops_lint.html#lintdisjunctiveassignmentinconstructor)
