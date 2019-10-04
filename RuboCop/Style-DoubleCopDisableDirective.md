Pattern: Double disable comments on one line

Issue: -

## Description

Detects double disable comments on one line. This is mostly to catch automatically generated comments that need to be regenerated.

## Examples

```ruby
# bad
def f # rubocop:disable Style/For # rubocop:disable Metrics/AbcSize
end

# good
# rubocop:disable Metrics/AbcSize
def f # rubocop:disable Style/For
end
# rubocop:enable Metrics/AbcSize

# if both fit on one line
def f # rubocop:disable Style/For, Metrics/AbcSize
end
```

## Further Reading

* [RuboCop - Style/DoubleCopDisableDirective](https://rubocop.readthedocs.io/en/latest/cops_style/#styledoublecopdisabledirective)
