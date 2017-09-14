Pattern: Braces around hash parameters

Issue: -

## Description

This cop checks for braces around the last parameter in a method call
if the last parameter is a hash.
It supports 3 styles:

* The `braces` style enforces braces around all method
parameters that are hashes.

* The `no_braces` style checks that the last parameter doesn't
have braces around it.

* The `context_dependent` style checks that the last parameter
doesn't have braces around it, but requires braces if the
second to last parameter is also a hash literal.

### Example

```ruby
# bad
some_method(x, y, a: 1, b: 2)

# good
some_method(x, y, {a: 1, b: 2})
```
```ruby
# bad
some_method(x, y, {a: 1, b: 2})

# good
some_method(x, y, a: 1, b: 2)
```
```ruby
# bad
some_method(x, y, {a: 1, b: 2})
some_method(x, y, {a: 1, b: 2}, a: 1, b: 2)

# good
some_method(x, y, a: 1, b: 2)
some_method(x, y, {a: 1, b: 2}, {a: 1, b: 2})
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | no_braces
SupportedStyles | braces, no_braces, context_dependent

## Further Reading

* [RuboCop - Style/BracesAroundHashParameters](https://rubocop.readthedocs.io/en/latest/cops_style/#stylebracesaroundhashparameters)
