Pattern: Style/WordArray

Issue: -

## Description

This cop can check for array literals made up of word-like
strings, that are not using the %w() syntax.

Alternatively, it can check for uses of the %w() syntax, in projects
which do not want to include that syntax.

Configuration option: MinSize
If set, arrays with fewer elements than this value will not trigger the
cop. For example, a `MinSize of `3` will not enforce a style on an array
of 2 or fewer elements.

### Example

```ruby
EnforcedStyle: percent (default)

# good
%w[foo bar baz]

# bad
['foo', 'bar', 'baz']
```
```ruby
EnforcedStyle: brackets

# good
['foo', 'bar', 'baz']

# bad
%w[foo bar baz]
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | percent
SupportedStyles | percent, brackets
MinSize | 0
WordRegex | (?-mix:\A[\p{Word}\n\t]+\z)

## Further Reading

* [RuboCop - Style/WordArray](https://rubocop.readthedocs.io/en/latest/cops_style/#stylewordarray)
* [https://github.com/bbatsov/ruby-style-guide#percent-w](https://github.com/bbatsov/ruby-style-guide#percent-w)
