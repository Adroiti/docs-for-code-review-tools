Pattern: Use of parallel assignment

Issue: -

## Description

Checks for simple usages of parallel assignment. Parallel assignment is less readable than separate assignment.

This will only complain when the number of variables being assigned matched the number of assigning variables.

## Examples

```ruby
# bad
a, b, c = 1, 2, 3
a, b, c = [1, 2, 3]

# good
one, two = *foo
a, b = foo()
a, b = b, a

a = 1
b = 2
c = 3
```

## Further Reading

* [RuboCop - Style/ParallelAssignment](https://rubocop.readthedocs.io/en/latest/cops_style/#styleparallelassignment)
* [https://github.com/bbatsov/ruby-style-guide#parallel-assignment](https://github.com/bbatsov/ruby-style-guide#parallel-assignment)
