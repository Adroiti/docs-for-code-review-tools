Pattern: Missing use of `be_invalid`/`not_to`

Issue: -

## Description

Enforces use of `be_invalid` or `not_to` for negated be_valid.

## Examples

#### EnforcedStyle: not_to (default)

```ruby
# bad
expect(foo).to be_invalid

# good
expect(foo).not_to be_valid
```

#### EnforcedStyle: be_invalid

```ruby
# bad
expect(foo).not_to be_valid

# good
expect(foo).to be_invalid
```

## Further Reading

* [RSpec/Rails/NegationBeValid](https://docs.rubocop.org/rubocop-rspec_rails/cops_rspecrails.html#rspecrailsnegationbevalid)
