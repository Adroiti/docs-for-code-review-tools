Pattern: Empty `when`

Issue: -

## Description

This cop checks for the presence of `when` branches without a body.

### Example

```ruby
# bad

case foo
when bar then 1
when baz then # nothing
end
```
```ruby
# good

case foo
when bar then 1
when baz then 2
end
```

## Further Reading

* [RuboCop - Lint/EmptyWhen](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintemptywhen)
