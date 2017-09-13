Pattern: Performance/RedundantMatch

Issue: -

## Description

This cop identifies use of `Regexp#match` or `String#match` in a context
where the integral return value of `=~` would do just as well.

### Example

```ruby
# bad
do_something if str.match(/regex/)
while regex.match('str')
  do_something
end

# good
method(str.match(/regex/))
return regex.match('str')
```

## Further Reading

* [RuboCop - Performance/RedundantMatch](https://rubocop.readthedocs.io/en/latest/cops_performance/#performanceredundantmatch)
