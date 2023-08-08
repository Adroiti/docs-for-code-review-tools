Pattern: Trailing comma in `Array` literal

Issue: -

## Description

This rule checks for trailing comma in array literals.

## Examples

#### EnforcedStyleForMultiline: consistent_comma

```ruby
# bad
a = [1, 2,]

# good
a = [
  1, 2,
  3,
]

# good
a = [
  1,
  2,
]
```
#### EnforcedStyleForMultiline: comma

```ruby
# bad
a = [1, 2,]

# good
a = [
  1,
  2,
]
```
#### EnforcedStyleForMultiline: no_comma (default)

```ruby
# bad
a = [1, 2,]

# good
a = [
  1,
  2
]
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyleForMultiline | `no_comma`

## Further Reading

* [RuboCop - Style/TrailingCommaInArrayLiteral](https://docs.rubocop.org/rubocop/cops_style.html#styletrailingcommainarrayliteral)
* [https://github.com/bbatsov/ruby-style-guide#no-trailing-array-commas](https://github.com/bbatsov/ruby-style-guide#no-trailing-array-commas)
