Pattern: Missing use of `String#start_with?`

Issue: -

## Description

This rule identifies unnecessary use of a Regex where `String#start_with?` would suffice.

## Examples

```ruby
# bad
'abc' =~ /\Aab/
'abc'.match(/\Aab/)

# good
'abc'.start_with?('ab')
```

## Further Reading

* [RuboCop - Performance/StartWith](https://github.com/rubocop-hq/rubocop-performance/blob/master/manual/cops_performance.md#performancestartwith)
* [https://github.com/JuanitoFatas/fast-ruby#stringmatch-vs-stringstart_withstringend_with-code-start-code-end](https://github.com/JuanitoFatas/fast-ruby#stringmatch-vs-stringstart_withstringend_with-code-start-code-end)
