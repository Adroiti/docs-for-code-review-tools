Pattern: Unnecessary `:` or `,` in `%i`

Issue: -

## Description

This rule checks for colons and commas in `%i`, e.g. `%i(:foo, :bar)`

It is more likely that the additional characters are unintended (for
example, mistranslating an array of literals to percent string notation)
rather than meant to be part of the resulting symbols.

## Examples

```ruby
# bad

%i(:foo, :bar)
```
```ruby
# good

%i(foo bar)
```

## Further Reading

* [RuboCop - Lint/ExtraCharactersInPercentSymbolArray](https://docs.rubocop.org/rubocop/cops_lint.html#lintextracharactersinpercentsymbolarray)
