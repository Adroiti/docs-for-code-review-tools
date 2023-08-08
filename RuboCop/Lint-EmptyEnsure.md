Pattern: Empty `ensure`

Issue: -

## Description

This rule checks for empty `ensure` blocks

## Examples

```ruby
# bad

def some_method
  do_something
ensure
end
```
```ruby
# bad

begin
  do_something
ensure
end
```
```ruby
# good

def some_method
  do_something
ensure
  do_something_else
end
```
```ruby
# good

begin
  do_something
ensure
  do_something_else
end
```

## Further Reading

* [RuboCop - Lint/EmptyEnsure](https://docs.rubocop.org/rubocop/cops_lint.html#lintemptyensure)
