Pattern: Use of `inject`/`reduce`

Issue: -

## Description

This cop looks for `inject`/`reduce` calls where the passed in object is
returned at the end and so could be replaced by `each_with_object` without
the need to return the object at the end.

### Example

```ruby
# bad
[1, 2].inject({}) { |a, e| a[e] = e; a }

# good
[1, 2].each_with_object({}) { |e, a| a[e] = e }
```

## Further Reading

* [RuboCop - Style/EachWithObject](https://rubocop.readthedocs.io/en/latest/cops_style/#styleeachwithobject)
