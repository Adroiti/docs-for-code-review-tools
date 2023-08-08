Pattern: Space after method name

Issue: -

## Description

Checks for space between a method name and a left parenthesis in defs.

## Examples

```ruby
# bad
def func (x) ... end

# good
def func(x) ... end
```

## Further Reading

* [RuboCop - Layout/SpaceAfterMethodName](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspaceaftermethodname)
* [https://github.com/bbatsov/ruby-style-guide#parens-no-spaces](https://github.com/bbatsov/ruby-style-guide#parens-no-spaces)
