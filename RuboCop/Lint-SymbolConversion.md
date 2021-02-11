Pattern: Use of symbol conversion

Issue: -

## Description

This rule checks for uses of literal strings converted to a symbol where a literal symbol could be used instead.

## Examples

```ruby
# bad
'string'.to_sym
:symbol.to_sym
'underscored_string'.to_sym
:'underscored_symbol'
'hyphenated-string'.to_sym

# good
:string
:symbol
:underscored_string
:underscored_symbol
:'hyphenated-string'
```

## Further Reading

* [RuboCop - Lint/SymbolConversion](https://docs.rubocop.org/rubocop/cops_lint.html#lintsymbolconversion)
