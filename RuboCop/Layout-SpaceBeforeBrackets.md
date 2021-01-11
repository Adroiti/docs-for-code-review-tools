Pattern: Use of space before brackets

Issue: -

## Description

Checks for space between the name of a receiver and a left brackets.

## Examples

```ruby
# bad
collection [index_or_key]

# good
collection[index_or_key]
```

## Further Reading

* [RuboCop - Layout/SpaceBeforeBrackets](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspacebeforebrackets)