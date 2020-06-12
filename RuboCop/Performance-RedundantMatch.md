Pattern: Redundant `#match`

Issue: -

## Description

This rule identifies use of `Regexp#match` or `String#match` in a context where the integral return value of `=~` would do just as well.

## Examples

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

* [RuboCop - Performance/RedundantMatch](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performanceredundantmatch)
* [https://github.com/JuanitoFatas/fast-ruby#regexp-vs-stringmatch-vs-string-code-](https://github.com/JuanitoFatas/fast-ruby#regexp-vs-stringmatch-vs-string-code-)
