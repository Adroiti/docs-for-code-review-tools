Pattern: And or

Issue: -

## Description

This cop checks for uses of `and` and `or`, and suggests using `&&` and
`|| instead`. It can be configured to check only in conditions, or in
all contexts.

### Example

```ruby
# EnforcedStyle: always (default)

# good
foo.save && return
if foo && bar

# bad
foo.save and return
if foo and bar
```
```ruby
# EnforcedStyle: conditionals

# good
foo.save && return
foo.save and return
if foo && bar

# bad
if foo and bar
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | always
SupportedStyles | always, conditionals

## Further Reading

* [RuboCop - Style/AndOr](https://rubocop.readthedocs.io/en/latest/cops_style/#styleandor)
* [https://github.com/bbatsov/ruby-style-guide#no-and-or-or](https://github.com/bbatsov/ruby-style-guide#no-and-or-or)
