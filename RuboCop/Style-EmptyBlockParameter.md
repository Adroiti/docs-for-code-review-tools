Pattern: Empty block parameter with pipe

Issue: -

## Description

This rule checks for pipes for empty block parameters. Pipes for empty
block parameters do not cause syntax errors, but they are redundant.

## Examples

```ruby
# bad
a do ||
  do_something
end

# bad
a { || do_something }

# good
a do
end

# good
a { do_something }
```

## Further Reading

* [RuboCop - Style/EmptyBlockParameter](https://docs.rubocop.org/rubocop/cops_style.html#styleemptyblockparameter)
