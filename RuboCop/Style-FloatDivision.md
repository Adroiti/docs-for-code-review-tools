Pattern: Division with integer coerced to float

Issue: -

## Description

It is recommended to either always use `fdiv` or coerce one side only. This rule also provides other options for code consistency.

## Examples

#### EnforcedStyle: single_coerce (default)

```ruby
# bad
a.to_f / b.to_f

# good
a.to_f / b
a / b.to_f
```
#### EnforcedStyle: left_coerce

```ruby
# bad
a / b.to_f
a.to_f / b.to_f

# good
a.to_f / b
```
#### EnforcedStyle: right_coerce

```ruby
# bad
a.to_f / b
a.to_f / b.to_f

# good
a / b.to_f
```
#### EnforcedStyle: fdiv

```ruby
# bad
a / b.to_f
a.to_f / b
a.to_f / b.to_f

# good
a.fdiv(b)
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `single_coerce` | `left_coerce`, `right_coerce`, `single_coerce`, `fdiv`

## Further Reading

* [RuboCop - Style/FloatDivision](https://rubocop.readthedocs.io/en/latest/cops_style/#stylefloatdivision)
