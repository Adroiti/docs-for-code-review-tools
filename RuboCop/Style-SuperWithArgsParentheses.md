Pattern: Missing use of parentheses in `super`

Issue: -

## Description

Enforces the presence of parentheses in `super` containing arguments.

`super` is a keyword and is provided as a distinct cop from those designed for method call.

## Examples

```ruby
# bad
super name, age

# good
super(name, age)
```
## Further Reading

* [RuboCop - SuperWithArgsParentheses](https://docs.rubocop.org/rubocop/cops_style.html#stylesuperwithargsparentheses)