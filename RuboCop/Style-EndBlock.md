Pattern: Use of `END` block

Issue: -

## Description

This cop checks for `END` blocks. Use `Kernel#at_exit` instead.

### Example

```ruby
# bad
END { puts 'Goodbye!' }

# good
at_exit { puts 'Goodbye!' }
```

## Further Reading

* [RuboCop - Style/EndBlock](https://rubocop.readthedocs.io/en/latest/cops_style/#styleendblock)
* [https://github.com/bbatsov/ruby-style-guide#no-END-blocks](https://github.com/bbatsov/ruby-style-guide#no-END-blocks)
