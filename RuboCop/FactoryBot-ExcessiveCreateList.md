Pattern: Excessive model creation in list

Issue: -

## Description

Checks for excessive model creation in a list.

## Examples

#### MaxAmount: 10 (default)

```ruby
# We do not allow more than 10 items to be created

# bad
create_list(:merge_request, 1000, state: :opened)

# good
create_list(:merge_request, 10, state: :opened)
```

## Further Reading

* [FactoryBot/ExcessiveCreateList](https://docs.rubocop.org/rubocop-factory_bot/cops_factorybot.html#factorybotexcessivecreatelist)