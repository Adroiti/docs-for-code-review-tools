Pattern: Use of logical operator in `unless`

Issue: -

## Description

Checks for the use of logical operators in an unless condition. It discourages such code, as the condition becomes more difficult to read and understand.

This rule supports two styles: 
	- `forbid_mixed_logical_operators` (default) 
	- `forbid_logical_operators`

`forbid_mixed_logical_operators` style forbids the use of more than one type of logical operators. This makes the unless condition easier to read because either all conditions need to be met or any condition need to be met in order for the expression to be truthy or falsey.

`forbid_logical_operators` style forbids any use of logical operator. This makes it even more easy to read the unless condition as there is only one condition in the expression.


## Examples

```ruby
# bad
return unless a || b && c
return unless a && b || c
return unless a && b and c
return unless a || b or c
return unless a && b or c
return unless a || b and c

# good
return unless a && b && c
return unless a || b || c
return unless a and b and c
return unless a or b or c
return unless a?
```

## Further Reading

* [RuboCop - Style/UnlessLogicalOperators](https://docs.rubocop.org/rubocop/cops_style.html#styleunlesslogicaloperators)
