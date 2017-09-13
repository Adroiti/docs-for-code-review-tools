Pattern: Lint/DuplicateCaseCondition

Issue: -

## Description

This cop checks that there are no repeated conditions
used in case 'when' expressions.

### Example

```ruby
# bad

case x
when 'first'
  do_something
when 'first'
  do_something_else
end
```
```ruby
# good

case x
when 'first'
  do_something
when 'second'
  do_something_else
end
```

## Further Reading

* [RuboCop - Lint/DuplicateCaseCondition](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintduplicatecasecondition)
