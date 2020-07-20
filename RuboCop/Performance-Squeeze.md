Pattern: Missing use of `squeeze` method

Issue: -

## Description

Identifies places where `gsub(/a+/, 'a'`) and `gsub!(/a+/, 'a')` can be replaced by `squeeze('a')` and `squeeze!('a')`.

## Examples

```ruby
# bad
str.gsub(/a+/, 'a')
str.gsub!(/a+/, 'a')

# good
str.squeeze('a')
str.squeeze!('a')
```

## Further Reading

* [RuboCop - Performance/Squeeze](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancesqueeze)