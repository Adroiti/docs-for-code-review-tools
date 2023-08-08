Pattern: Use of `END` block

Issue: -

## Description

This rule checks for `END` blocks. Use `Kernel#at_exit` instead.

## Examples

```ruby
# bad
END { puts 'Goodbye!' }

# good
at_exit { puts 'Goodbye!' }
```

## Further Reading

* [RuboCop - Style/EndBlock](https://docs.rubocop.org/rubocop/cops_style.html#styleendblock)
* [https://github.com/bbatsov/ruby-style-guide#no-END-blocks](https://github.com/bbatsov/ruby-style-guide#no-END-blocks)
