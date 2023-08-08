Pattern: Space after `:`

Issue: -

## Description

Checks for colon (`:`) not followed by some kind of space. This rule does not handle spaces after a ternary operator.

## Examples

```ruby
# bad
def f(a:, b:2); {a:3}; end

# good
def f(a:, b: 2); {a: 3}; end
```

## Further Reading

* [RuboCop - Layout/SpaceAfterColon](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspaceaftercolon)
* [https://github.com/bbatsov/ruby-style-guide#spaces-operators](https://github.com/bbatsov/ruby-style-guide#spaces-operators)
