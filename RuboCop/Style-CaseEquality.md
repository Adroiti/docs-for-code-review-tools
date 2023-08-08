Pattern: Use of case equality operator (`===`)

Issue: -

## Description

This rule checks for uses of the case equality operator (`===`). As its name implies it is meant to be used implicitly by `case` expressions and outside of them it yields confusing code.

## Examples

```ruby
# bad
Array === something
(1..100) === 7
/something/ === some_string

# good
something.is_a?(Array)
(1..100).include?(7)
some_string =~ /something/
```

## Further Reading

* [RuboCop - Style/CaseEquality](https://docs.rubocop.org/rubocop/cops_style.html#stylecaseequality)
* [https://github.com/bbatsov/ruby-style-guide#no-case-equality](https://github.com/bbatsov/ruby-style-guide#no-case-equality)
