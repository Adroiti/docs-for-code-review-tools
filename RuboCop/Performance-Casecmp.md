Pattern: Missing use of `casecmp`

Issue: -

## Description

This rule identifies places where a case-insensitive string comparison can better be implemented using `casecmp`.

## Examples

```ruby
# bad
str.downcase == 'abc'
str.upcase.eql? 'ABC'
'abc' == str.downcase
'ABC'.eql? str.upcase
str.downcase == str.downcase

# good
str.casecmp('ABC').zero?
'abc'.casecmp(str).zero?
```

## Further Reading

* [RuboCop - Performance/Casecmp](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancecasecmp)
* [https://github.com/JuanitoFatas/fast-ruby#stringcasecmp-vs-stringdowncase---code](https://github.com/JuanitoFatas/fast-ruby#stringcasecmp-vs-stringdowncase---code)
