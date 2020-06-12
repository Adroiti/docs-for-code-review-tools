Pattern: Use of double `#start_with?`/`#end_with?`

Issue: -

## Description

This rule checks for double `#start_with?` or `#end_with?` calls separated by `||`. In some cases such calls can be replaced with an single `#start_with?`/`#end_with?` call.

## Examples

```ruby
# bad
str.start_with?("a") || str.start_with?(Some::CONST)
str.start_with?("a", "b") || str.start_with?("c")
var1 = ...
var2 = ...
str.end_with?(var1) || str.end_with?(var2)

# good
str.start_with?("a", Some::CONST)
str.start_with?("a", "b", "c")
var1 = ...
var2 = ...
str.end_with?(var1, var2)
```

## Default configuration

Attribute | Value
--- | ---
IncludeActiveSupportAliases | false

## Further Reading

* [RuboCop - Performance/DoubleStartEndWith](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancedoublestartendwith)
