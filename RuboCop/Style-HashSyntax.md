Pattern: Inconsistent hash syntax

Issue: -

## Description

This rule checks hash literal syntax.

It can enforce either the use of the class hash rocket syntax or
the use of the newer Ruby 1.9 syntax (when applicable).

A separate offense is registered for each problematic pair.

The supported styles are:

* ruby19 - forces use of the 1.9 syntax (e.g. `{a: 1}`) when hashes have
  all symbols for keys
* hash_rockets - forces use of hash rockets for all hashes
* no_mixed_keys - simply checks for hashes with mixed syntaxes
* ruby19_no_mixed_keys - forces use of ruby 1.9 syntax and forbids mixed
  syntax hashes

## Examples

```ruby
"EnforcedStyle => 'ruby19'"

# good
{a: 2, b: 1}
{:c => 2, 'd' => 2} # acceptable since 'd' isn't a symbol
{d: 1, 'e' => 2} # technically not forbidden

# bad
{:a => 2}
{b: 1, :c => 2}
```
```ruby
"EnforcedStyle => 'hash_rockets'"

# good
{:a => 1, :b => 2}

# bad
{a: 1, b: 2}
{c: 1, 'd' => 5}
```
```ruby
"EnforcedStyle => 'no_mixed_keys'"

# good
{:a => 1, :b => 2}
{c: 1, d: 2}

# bad
{:a => 1, b: 2}
{c: 1, 'd' => 2}
```
```ruby
"EnforcedStyle => 'ruby19_no_mixed_keys'"

# good
{a: 1, b: 2}
{:c => 3, 'd' => 4}

# bad
{:a => 1, :b => 2}
{c: 2, 'd' => 3} # should just use hash rockets
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | ruby19
SupportedStyles | ruby19, hash_rockets, no_mixed_keys, ruby19_no_mixed_keys
UseHashRocketsWithSymbolValues | false
PreferHashRocketsForNonAlnumEndingSymbols | false

## Further Reading

* [RuboCop - Style/HashSyntax](https://docs.rubocop.org/rubocop/cops_style.html#stylehashsyntax)
* [https://github.com/bbatsov/ruby-style-guide#hash-literals](https://github.com/bbatsov/ruby-style-guide#hash-literals)
