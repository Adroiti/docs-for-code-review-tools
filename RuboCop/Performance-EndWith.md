Pattern: Missing use of `String#end_with?`

Issue: -

## Description

This rule identifies unnecessary use of a regex where `String#end_with?` would suffice.

## Examples

```ruby
# bad
'abc' =~ /bc\Z/
'abc'.match(/bc\Z/)

# good
'abc'.end_with?('bc')
```

## Further Reading

* [RuboCop - Performance/EndWith](https://rubocop.readthedocs.io/en/latest/cops_performance/#performanceendwith)
* [https://github.com/JuanitoFatas/fast-ruby#stringmatch-vs-stringstart_withstringend_with-code-start-code-end](https://github.com/JuanitoFatas/fast-ruby#stringmatch-vs-stringstart_withstringend_with-code-start-code-end)
