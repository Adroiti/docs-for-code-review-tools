Pattern: Missing use of bitwise predicate

Issue: -

## Description

Prefer bitwise predicate methods over direct comparison operations.

## Examples

```rb
# bad - checks any set bits
(variable & flags).positive?

# good
variable.anybits?(flags)

# bad - checks all set bits
(variable & flags) == flags

# good
variable.allbits?(flags)

# bad - checks no set bits
(variable & flags).zero?

# good
variable.nobits?(flags)
```

## Further Reading

* [RuboCop - Style/BitwisePredicate](https://docs.rubocop.org/rubocop/cops_style.html#stylebitwisepredicate)
