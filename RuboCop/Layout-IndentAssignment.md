Pattern: Layout/IndentAssignment

Issue: -

## Description

This cop checks the indentation of the first line of the
right-hand-side of a multi-line assignment.

The indentation of the remaining lines can be corrected with
other cops such as `IndentationConsistency` and `EndAlignment`.

### Example

```ruby
# bad
value =
if foo
  'bar'
end

# good
value =
  if foo
    'bar'
  end
```

## Default configuration

Attribute | Value
--- | ---
IndentationWidth |

## Further Reading

* [RuboCop - Layout/IndentAssignment](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutindentassignment)
