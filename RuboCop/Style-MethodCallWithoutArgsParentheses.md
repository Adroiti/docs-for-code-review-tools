Pattern: Parentheses for method call with no arguments

Issue: -

## Description

This rule checks for unwanted parentheses in parameterless method calls.

## Examples

```ruby
# bad
object.some_method()

# good
object.some_method
```

## Further Reading

* [RuboCop - Style/MethodCallWithoutArgsParentheses](https://docs.rubocop.org/rubocop/cops_style.html#stylemethodcallwithoutargsparentheses)
* [https://github.com/bbatsov/ruby-style-guide#method-invocation-parens](https://github.com/bbatsov/ruby-style-guide#method-invocation-parens)
