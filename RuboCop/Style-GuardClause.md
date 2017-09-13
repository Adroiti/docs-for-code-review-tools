Pattern: Style/GuardClause

Issue: -

## Description

Use a guard clause instead of wrapping the code inside a conditional
expression

### Example

```ruby
# bad
def test
  if something
    work
  end
end

# good
def test
  return unless something
  work
end

# also good
def test
  work if something
end

# bad
if something
  raise 'exception'
else
  ok
end

# good
raise 'exception' if something
ok
```

## Default configuration

Attribute | Value
--- | ---
MinBodyLength | 1

## Further Reading

* [RuboCop - Style/GuardClause](https://rubocop.readthedocs.io/en/latest/cops_style/#styleguardclause)
* [https://github.com/bbatsov/ruby-style-guide#no-nested-conditionals](https://github.com/bbatsov/ruby-style-guide#no-nested-conditionals)
