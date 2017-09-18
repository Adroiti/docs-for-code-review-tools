Pattern: Using `rescue` in its modifier form

Issue: -

## Description

This rule checks for uses of rescue in its modifier form.

## Examples

```ruby
# bad - this catches exceptions of StandardError class and its descendant classes
read_file rescue handle_error($!)

# good - this catches only the exceptions of Errno::ENOENT class and its descendant classes
def foo
  read_file
rescue Errno::ENOENT => ex
  handle_error(ex)
end
```

## Further Reading

* [RuboCop - Style/RescueModifier](https://rubocop.readthedocs.io/en/latest/cops_style/#stylerescuemodifier)
* [https://github.com/bbatsov/ruby-style-guide#no-rescue-modifiers](https://github.com/bbatsov/ruby-style-guide#no-rescue-modifiers)
