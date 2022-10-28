Pattern: Passing argument to `#to_s`

Issue: -

## Description

Identifies passing any argument to `#to_s`.

## Examples

```ruby
# bad
obj.to_s(:delimited)

# good
obj.to_formatted_s(:delimited)
```
## Further Reading

* [Rails - Rails/ToSWithArgument](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railstoswithargument)
