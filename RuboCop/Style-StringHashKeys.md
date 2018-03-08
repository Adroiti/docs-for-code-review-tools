Pattern: Use of string as hash key

Issue: -

## Description

This rule checks for the use of strings as keys in hashes. The use of symbols is preferred instead.

## Examples

```ruby
# bad
{ 'one' => 1, 'two' => 2, 'three' => 3 }

# good
{ one: 1, two: 2, three: 3 }
```

## Further Reading

* [RuboCop - Style/StringHashKeys](https://rubocop.readthedocs.io/en/latest/cops_style/#stylestringhashkeys)
* [https://github.com/bbatsov/ruby-style-guide#symbols-as-keys](https://github.com/bbatsov/ruby-style-guide#symbols-as-keys)
