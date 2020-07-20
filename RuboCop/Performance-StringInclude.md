Pattern: Missing use of `String#include?`

Issue: -

## Description

Identifies unnecessary use of a regex where `String#include?` would suffice.

## Examples

```ruby
# bad
'abc'.match?(/ab/)
/ab/.match?('abc')
'abc' =~ /ab/
/ab/ =~ 'abc'
'abc'.match(/ab/)
/ab/.match('abc')

# good
'abc'.include?('ab')
```

## Further Reading

* [RuboCop - Performance/StringInclude](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancestringinclude)