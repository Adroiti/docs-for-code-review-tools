Pattern: Use of deprecated flip-flop operator

Issue: -

## Description

flip-flop operator is deprecated since Ruby 2.6.0.

### Examples

```ruby
# bad
(1..20).each do |x|
  puts x if (x == 5) .. (x == 10)
end

# good
(1..20).each do |x|
  puts x if (x >= 5) && (x <= 10)
end
```

## Further Reading

* [RuboCop - Lint/FlipFlop](https://docs.rubocop.org/rubocop/cops_lint.html#lintflipflop)