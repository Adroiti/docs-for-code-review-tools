Pattern: Malformed braces around hash as last array item

Issue: -

## Description

Checks for presence or absence of braces around hash literal as a last array item depending on configuration.

## Examples

```ruby
# bad
[1, 2, one: 1, two: 2]

# good
[1, 2, { one: 1, two: 2 }]
```

## Further Reading

* [RuboCop - Style/HashAsLastArrayItem](https://docs.rubocop.org/rubocop/cops_style.html#stylehashaslastarrayitem)
