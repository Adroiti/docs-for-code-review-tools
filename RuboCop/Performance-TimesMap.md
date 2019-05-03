Pattern: Use of `.times.map`

Issue: -

## Description

This rule checks for `.times.map` calls. In most cases such calls can be replaced with an explicit array creation.

## Examples

```ruby
# bad
9.times.map do |i|
  i.to_s
end

# good
Array.new(9) do |i|
  i.to_s
end
```

## Further Reading

* [RuboCop - Performance/TimesMap](https://github.com/rubocop-hq/rubocop-performance/blob/master/manual/cops_performance.md#performancetimesmap)
