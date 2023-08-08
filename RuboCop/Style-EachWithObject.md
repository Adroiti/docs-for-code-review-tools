Pattern: Use of `inject`/`reduce`

Issue: -

## Description

This rule looks for `inject`/`reduce` calls where the passed in object is
returned at the end and so could be replaced by `each_with_object` without
the need to return the object at the end.

## Examples

```ruby
# bad
[1, 2].inject({}) { |a, e| a[e] = e; a }

# good
[1, 2].each_with_object({}) { |e, a| a[e] = e }
```

## Further Reading

* [RuboCop - Style/EachWithObject](https://docs.rubocop.org/rubocop/cops_style.html#styleeachwithobject)
