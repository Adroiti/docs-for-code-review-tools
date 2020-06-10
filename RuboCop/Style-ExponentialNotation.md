Pattern: Inconsistent exponential notation

Issue: -

## Description

This rule enforces consistency when using exponential notation for numbers in the code (eg 1.2e4). Different styles are supported:
* `scientific` which enforces a mantissa between 1 (inclusive) and 10 (exclusive).
* `engineering` which enforces the exponent to be a multiple of 3 and the mantissa to be between 0.1 (inclusive) and 10 (exclusive).
* `integral` which enforces the mantissa to always be a whole number without trailing zeroes.

## Examples

### EnforcedStyle: scientific (default)

```ruby
# Enforces a mantissa between 1 (inclusive) and 10 (exclusive).

# bad
10e6
0.3e4
11.7e5
3.14e0

# good
1e7
3e3
1.17e6
3.14
```

### EnforcedStyle: integral

```ruby
# Enforces the mantissa to have no decimal part and no
# trailing zeroes.

# bad
3.2e7
0.1e5
120e4

# good
32e6
1e4
12e5
```

## Further Reading

* [RuboCop - Style/ExponentialNotation](https://docs.rubocop.org/rubocop/cops_style.html#styleexponentialnotation)
