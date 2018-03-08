Pattern: Use of random number with offset

Issue: -

## Description

This rule checks for the use of randomly generated numbers, added/subtracted with integer literals, as well as those with `Integer#succ` and `Integer#pred` methods. Prefer using ranges instead as it clearly states the intentions.

## Examples

```ruby
# bad
rand(6) + 1
1 + rand(6)
rand(6) - 1
1 - rand(6)
rand(6).succ
rand(6).pred
Random.rand(6) + 1
Kernel.rand(6) + 1
rand(0..5) + 1

# good
rand(1..6)
rand(1...7)
```

## Further Reading

* [RuboCop - Style/RandomWithOffset](https://rubocop.readthedocs.io/en/latest/cops_style/#stylerandomwithoffset)
* [https://github.com/bbatsov/ruby-style-guide#random-numbers](https://github.com/bbatsov/ruby-style-guide#random-numbers)
