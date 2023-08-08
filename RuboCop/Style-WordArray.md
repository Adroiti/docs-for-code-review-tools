Pattern: Use of literal array syntax instead of `%w`

Issue: -

## Description

This rule can check for array literals made up of word-like
strings, that are not using the `%w` syntax.

Alternatively, it can check for uses of the `%w` syntax, in projects
which do not want to include that syntax.

Configuration option: `MinSize`
If set, arrays with fewer elements than this value will not trigger the
cop. For example, a `MinSize of 3` will not enforce a style on an array
of 2 or fewer elements.

## Examples

```ruby
# bad
STATES = ['draft', 'open', 'closed']

# good
STATES = %w[draft open closed]
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | percent
SupportedStyles | percent, brackets
MinSize | 0
WordRegex | (?-mix:\A[\p{Word}\n\t]+\z)

## Further Reading

* [RuboCop - Style/WordArray](https://docs.rubocop.org/rubocop/cops_style.html#stylewordarray)
* [https://github.com/bbatsov/ruby-style-guide#percent-w](https://github.com/bbatsov/ruby-style-guide#percent-w)
