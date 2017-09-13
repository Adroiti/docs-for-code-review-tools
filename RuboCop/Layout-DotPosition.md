Pattern: Layout/DotPosition

Issue: -

## Description

This cop checks the . position in multi-line method calls.

### Example

```ruby
# bad
something.
  mehod

# good
something
  .method
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | leading
SupportedStyles | leading, trailing

## Further Reading

* [RuboCop - Layout/DotPosition](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutdotposition)
* [https://github.com/bbatsov/ruby-style-guide#consistent-multi-line-chains](https://github.com/bbatsov/ruby-style-guide#consistent-multi-line-chains)
