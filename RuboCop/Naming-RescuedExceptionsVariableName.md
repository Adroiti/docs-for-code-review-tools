Pattern: Invalid rescued exception variable name

Issue: -

## Description

Makes sure that rescued exceptions variables are named as expected.

The `PreferredName` config option takes a `String`. It represents the required name of the variable. Its default is `e`.

## Examples

#### PreferredName: e (default)

```ruby
# bad
begin
  # do something
rescue MyException => exception
  # do something
end

# good
begin
  # do something
rescue MyException => e
  # do something
end

# good
begin
  # do something
rescue MyException => _e
  # do something
end
```
#### PreferredName: exception

```ruby
# bad
begin
  # do something
rescue MyException => e
  # do something
end

# good
begin
  # do something
rescue MyException => exception
  # do something
end

# good
begin
  # do something
rescue MyException => _exception
  # do something
end
```

## Configurable attributes

Name | Default value
--- | ---
PreferredName | `e`

## Further Reading

* [RuboCop - Naming/RescuedExceptionsVariableName](https://rubocop.readthedocs.io/en/latest/cops_naming/#namingrescuedexceptionsvariablename)
