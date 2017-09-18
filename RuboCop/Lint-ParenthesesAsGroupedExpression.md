Pattern: `(...)` interpreted as grouped expression

Issue: -

## Description

Checks for space between a the name of a called method and a left parenthesis.

## Examples

```ruby
# bad

puts (x + y)
```
```ruby
# good

puts(x + y)
```

## Further Reading

* [RuboCop - Lint/ParenthesesAsGroupedExpression](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintparenthesesasgroupedexpression)
* [https://github.com/bbatsov/ruby-style-guide#parens-no-spaces](https://github.com/bbatsov/ruby-style-guide#parens-no-spaces)
