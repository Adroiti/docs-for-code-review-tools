Pattern: Trailing comma in `Hash` literal

Issue: -

## Description

This rule checks for trailing comma in hash literals.

## Examples

#### EnforcedStyleForMultiline: consistent_comma

```ruby
# bad
a = { foo: 1, bar: 2, }

# good
a = {
  foo: 1, bar: 2,
  qux: 3,
}

# good
a = {
  foo: 1,
  bar: 2,
}
```
#### EnforcedStyleForMultiline: comma

```ruby
# bad
a = { foo: 1, bar: 2, }

# good
a = {
  foo: 1,
  bar: 2,
}
```
#### EnforcedStyleForMultiline: no_comma (default)

```ruby
# bad
a = { foo: 1, bar: 2, }

# good
a = {
  foo: 1,
  bar: 2
}
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyleForMultiline | `no_comma`

## Further Reading

* [RuboCop - Style/TrailingCommaInHashLiteral](https://docs.rubocop.org/rubocop/cops_style.html#styletrailingcommainhashliteral)
