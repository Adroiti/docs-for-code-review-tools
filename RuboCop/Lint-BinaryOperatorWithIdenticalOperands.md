Pattern: Use of binary operator with same operands

Issue: -

## Description

This rule checks for places where binary operator has identical operands.

It covers arithmetic operators: `+`, `-`, `*`, `/`, `%`, `**`;
comparison operators: `==`, `===`, `=~`, `>`, `>=`, `<`, `<=`;
bitwise operators: `|`, `^`, `&`, `<<`, `>>`;
boolean operators: `&&`, `||`
and "spaceship" operator - `<=>`.

This rule is marked as unsafe as it does not consider side effects when calling methods
and thus can generate false positives:
  if wr.take_char == '\0' && wr.take_char == '\0'

## Examples

```ruby
# bad
x.top >= x.top

if a.x != 0 && a.x != 0
  do_something
end

def childs?
  left_child || left_child
end
```

## Further Reading

* [RuboCop - Lint/BinaryOperatorWithIdenticalOperands](https://docs.rubocop.org/rubocop/cops_lint.html#lintbinaryoperatorwithidenticaloperands)
