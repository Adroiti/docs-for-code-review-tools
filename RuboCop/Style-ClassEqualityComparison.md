Pattern: Missing use of `Object#instance_of?`

Issue: -

## Description

Enforces the use of `Object#instance_of?` instead of class comparison for equality.

## Examples

```ruby
# bad
var.class == Date
var.class.equal?(Date)
var.class.eql?(Date)
var.class.name == 'Date'

# good
var.instance_of?(Date)
```

## Further Reading

* [RuboCop - Style/ClassEqualityComparison](https://docs.rubocop.org/rubocop/cops_style.html#styleclassequalitycomparison)
