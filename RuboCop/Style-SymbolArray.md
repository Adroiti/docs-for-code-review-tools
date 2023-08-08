Pattern: Use of literal array syntax instead of `%i`

Issue: -

## Description

This rule can check for array literals made up of symbols that are not
using the `%i` syntax.

Alternatively, it checks for symbol arrays using the `%i` syntax on
projects which do not want to use that syntax, perhaps because they
support a version of Ruby lower than 2.0.

Configuration option: MinSize
If set, arrays with fewer elements than this value will not trigger the
cop. For example, a `MinSize of 3` will not enforce a style on an array
of 2 or fewer elements.

## Examples

```ruby
# bad
STATES = [:draft, :open, :closed]

# good
STATES = %i[draft open closed]
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | percent
MinSize | 0
SupportedStyles | percent, brackets

## Further Reading

* [RuboCop - Style/SymbolArray](https://docs.rubocop.org/rubocop/cops_style.html#stylesymbolarray)
* [https://github.com/bbatsov/ruby-style-guide#percent-i](https://github.com/bbatsov/ruby-style-guide#percent-i)
