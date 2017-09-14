Pattern: Parentheses for method call with no arguments

Issue: -

## Description

This cop checks for unwanted parentheses in parameterless method calls.

### Example

```ruby
# bad
object.some_method()

# good
object.some_method
```

## Further Reading

* [RuboCop - Style/MethodCallWithoutArgsParentheses](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemethodcallwithoutargsparentheses)
* [https://github.com/bbatsov/ruby-style-guide#method-invocation-parens](https://github.com/bbatsov/ruby-style-guide#method-invocation-parens)
