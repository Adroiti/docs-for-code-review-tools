Pattern: Unused `casecmp`

Issue: -

## Description

This cop identifies places where a case-insensitive string comparison can better be implemented using `casecmp`.

### Example

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

* [RuboCop - Performance/Casecmp](https://rubocop.readthedocs.io/en/latest/cops_performance/#performancecasecmp)
* [https://github.com/JuanitoFatas/fast-ruby#stringcasecmp-vs-stringdowncase---code](https://github.com/JuanitoFatas/fast-ruby#stringcasecmp-vs-stringdowncase---code)
