Pattern: Malformed block parameter name

Issue: -

## Description

This rule checks block parameter names for how descriptive they
are. It is highly configurable.

The `MinNameLength` config option takes an integer. It represents
the minimum amount of characters the name must be. Its default is 1.
The `AllowNamesEndingInNumbers` config option takes a boolean. When
set to false, this rule will register offenses for names ending with
numbers. Its default is false. The `AllowedNames` config option
takes an array of whitelisted names that will never register an
offense. The `ForbiddenNames` config option takes an array of
blacklisted names that will always register an offense.

## Examples

```ruby
# bad
bar do |varOne, varTwo|
  varOne + varTwo
end

# With `AllowNamesEndingInNumbers` set to false
foo { |num1, num2| num1 * num2 }

# With `MinParamNameLength` set to number greater than 1
baz { |a, b, c| do_stuff(a, b, c) }

# good
bar do |thud, fred|
  thud + fred
end

foo { |speed, distance| speed * distance }

baz { |age, height, gender| do_stuff(age, height, gender) }
```

## Default configuration

Attribute | Value
--- | ---
MinNameLength | `1`
AllowNamesEndingInNumbers | `true`
AllowedNames | `[]`
ForbiddenNames | `[]`

## Further Reading

* [RuboCop - Naming/BlockParameterName](https://docs.rubocop.org/rubocop/cops_naming.html#namingblockparamname)
