Pattern: Positional argument in http method call

Issue: -

## Description

This cop is used to identify usages of http methods like `get`, `post`,
`put`, `patch` without the usage of keyword arguments in your tests and
change them to use keyword args.

### Example

```ruby
# bad
get :new, { user_id: 1}

# good
get :new, params: { user_id: 1 }
```

## Default configuration

Attribute | Value
--- | ---
Include | spec/\*\*/\*, test/\*\*/\*

## Further Reading

* [RuboCop - Rails/HttpPositionalArguments](https://rubocop.readthedocs.io/en/latest/cops_rails/#railshttppositionalarguments)
