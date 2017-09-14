Pattern: Numeric predicate

Issue: -

## Description

This cop checks for usage of comparison operators (`==`,
`>`, `<`) to test numbers as zero, positive, or negative.
These can be replaced by their respective predicate methods.
The cop can also be configured to do the reverse.

The cop disregards `#nonzero?` as it its value is truthy or falsey,
but not `true` and `false`, and thus not always interchangeable with
`!= 0`.

The cop ignores comparisons to global variables, since they are often
populated with objects which can be compared with integers, but are
not themselves `Interger` polymorphic.

### Example

```ruby
# EnforcedStyle: predicate (default)

# bad

foo == 0
0 > foo
bar.baz > 0

# good

foo.zero?
foo.negative?
bar.baz.positive?
```
```ruby
# EnforcedStyle: comparison

# bad

foo.zero?
foo.negative?
bar.baz.positive?

# good

foo == 0
0 > foo
bar.baz > 0
```

## Default configuration

Attribute | Value
--- | ---
AutoCorrect | false
EnforcedStyle | predicate
SupportedStyles | predicate, comparison
Exclude | spec/\*\*/\*

## Further Reading

* [RuboCop - Style/NumericPredicate](https://rubocop.readthedocs.io/en/latest/cops_style/#stylenumericpredicate)
* [https://github.com/bbatsov/ruby-style-guide#predicate-methods](https://github.com/bbatsov/ruby-style-guide#predicate-methods)
