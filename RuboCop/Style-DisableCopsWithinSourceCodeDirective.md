Pattern: Comment to disable/enable RuboCop

Issue: -

## Description

Detects comments to enable/disable RuboCop. This is useful if want to make sure that every RuboCop error gets fixed and not quickly disabled with a comment.

## Examples

```ruby
# bad
# rubocop:disable Metrics/AbcSize
def f
end
# rubocop:enable Metrics/AbcSize

# good
def fixed_method_name_and_no_rubocop_comments
end
```

## Further Reading

* [RuboCop - Style/DisableCopsWithinSourceCodeDirective](https://docs.rubocop.org/rubocop/cops_style.html#styledisablecopswithinsourcecodedirective)
