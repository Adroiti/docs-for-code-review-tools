Pattern: Performance/EndWith

Issue: -

## Description

This cop identifies unnecessary use of a regex where `String#end_with?`
would suffice.

### Example

```ruby
# bad
'abc' =~ /bc\Z/
'abc'.match(/bc\Z/)

# good
'abc'.end_with?('bc')
```

## Default configuration

Attribute | Value
--- | ---
AutoCorrect | false

## Further Reading

* [RuboCop - Performance/EndWith](https://rubocop.readthedocs.io/en/latest/cops_performance/#performanceendwith)
* [https://github.com/JuanitoFatas/fast-ruby#stringmatch-vs-stringstart_withstringend_with-code-start-code-end](https://github.com/JuanitoFatas/fast-ruby#stringmatch-vs-stringstart_withstringend_with-code-start-code-end)
