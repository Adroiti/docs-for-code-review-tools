Pattern: Empty `ensure`

Issue: -

## Description

This cop checks for empty `ensure` blocks

### Example

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

## Default configuration

Attribute | Value
--- | ---
AutoCorrect | false

## Further Reading

* [RuboCop - Lint/EmptyEnsure](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintemptyensure)
