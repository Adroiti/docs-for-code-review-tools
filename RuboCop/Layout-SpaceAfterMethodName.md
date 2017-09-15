Pattern: Space after method name

Issue: -

## Description

Checks for space between a method name and a left parenthesis in defs.

### Example

```ruby
# bad
def func (x) ... end

# good
def func(x) ... end
```

## Further Reading

* [RuboCop - Layout/SpaceAfterMethodName](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutspaceaftermethodname)
* [https://github.com/bbatsov/ruby-style-guide#parens-no-spaces](https://github.com/bbatsov/ruby-style-guide#parens-no-spaces)
