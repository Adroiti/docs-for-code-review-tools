Pattern: Duplicate `case` condition

Issue: -

## Description

This rule checks that there are no repeated conditions used in `case when` expressions.

## Examples

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

* [RuboCop - Lint/DuplicateCaseCondition](https://docs.rubocop.org/rubocop/cops_lint.html#lintduplicatecasecondition)
