Pattern: Unused `String#start_with?`

Issue: -

## Description

This cop identifies unnecessary use of a Regex where `String#start_with?` would suffice.

### Example

```ruby
# bad
'abc' =~ /\Aab/
'abc'.match(/\Aab/)

# good
'abc'.start_with?('ab')
```

## Default configuration

Attribute | Value
--- | ---
AutoCorrect | false

## Further Reading

* [RuboCop - Performance/StartWith](https://rubocop.readthedocs.io/en/latest/cops_performance/#performancestartwith)
* [https://github.com/JuanitoFatas/fast-ruby#stringmatch-vs-stringstart_withstringend_with-code-start-code-end](https://github.com/JuanitoFatas/fast-ruby#stringmatch-vs-stringstart_withstringend_with-code-start-code-end)
