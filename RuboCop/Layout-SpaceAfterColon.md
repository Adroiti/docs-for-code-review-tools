Pattern: Layout/SpaceAfterColon

Issue: -

## Description

Checks for colon (:) not followed by some kind of space.
N.B. this cop does not handle spaces after a ternary operator, which are
instead handled by Layout/SpaceAroundOperators.

### Example

```ruby
# bad
def f(a:, b:2); {a:3}; end

# good
def f(a:, b: 2); {a: 3}; end
```

## Further Reading

* [RuboCop - Layout/SpaceAfterColon](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutspaceaftercolon)
* [https://github.com/bbatsov/ruby-style-guide#spaces-operators](https://github.com/bbatsov/ruby-style-guide#spaces-operators)
