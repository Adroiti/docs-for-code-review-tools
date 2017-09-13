Pattern: Lint/ShadowedException

Issue: -

## Description

This cop checks for a rescued exception that get shadowed by a
less specific exception being rescued before a more specific
exception is rescued.

### Example

```ruby
# bad

begin
  something
rescue Exception
  handle_exception
rescue StandardError
  handle_standard_error
end
```
```ruby
# good

begin
  something
rescue StandardError
  handle_standard_error
rescue Exception
  handle_exception
end
```

## Further Reading

* [RuboCop - Lint/ShadowedException](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintshadowedexception)
