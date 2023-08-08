Pattern: Redundant argument

Issue: -

## Description

Checks for a redundant argument passed to certain methods.

Limitations:

    This cop matches for method names only and hence cannot tell apart methods with same name in different classes.

    This cop is limited to methods with single parameter.

    This cop is unsafe if certain special global variables (e.g. `$;`) are set. That depends on the nature of the target methods, of course.

Method names and their redundant arguments can be configured like this:

Methods: join: '' split: ' ' foo: 2

## Examples

```ruby
# bad
array.join('')
[1, 2, 3].join("")
string.split(" ")
"first\nsecond".split(" ")
A.foo(2)

# good
array.join
[1, 2, 3].join
string.split
"first second".split
A.foo
```

## Further Reading

* [RuboCop - Style/RedundantArgument](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantargument)
