Pattern: Duplicate `elsif` condition

Issue: -

## Description

Checks that there are no repeated conditions used in if `elsif`.

## Examples

```ruby
# bad
if x == 1
  do_something
elsif x == 1
  do_something_else
end

# good
if x == 1
  do_something
elsif x == 2
  do_something_else
end
```

## Further Reading

* [RuboCop - Lint/DuplicateElsifCondition](https://docs.rubocop.org/rubocop/cops_lint.html#lintduplicateelsifcondition)
