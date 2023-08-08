Pattern: Nested ternary operator

Issue: -

## Description

Use one expression per branch in a ternary operator. This also means that ternary operators must not be nested. Prefer `if`/`else` constructs in these cases.

## Examples

```ruby
# bad
some_condition ? (nested_condition ? nested_something : nested_something_else) : something_else

# good
if some_condition
  nested_condition ? nested_something : nested_something_else
else
  something_else
end
```

## Further Reading

* [RuboCop - Style/NestedTernaryOperator](https://docs.rubocop.org/rubocop/cops_style.html#stylenestedternaryoperator)
* [https://github.com/bbatsov/ruby-style-guide#no-nested-ternary](https://github.com/bbatsov/ruby-style-guide#no-nested-ternary)
