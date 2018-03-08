Pattern: Trailing code after module definition

Issue: -

## Description

This rule checks for trailing code after the module definition. Place the first line of module body on its own line.

## Examples

```ruby
# bad
module Foo extend self
end

# good
module Foo
  extend self
end
```

## Further Reading

* [RuboCop - Style/TrailingBodyOnModule](https://rubocop.readthedocs.io/en/latest/cops_style/#styletrailingbodyonmodule)
