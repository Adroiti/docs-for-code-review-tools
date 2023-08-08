Pattern: Wrong alias

Issue: -

## Description

This rule enforces the use of either `#alias` or `#alias_method`
depending on configuration.
It also flags uses of `alias :symbol` rather than `alias bareword`.

## Examples

```ruby
# EnforcedStyle: prefer_alias

# good
alias bar foo

# bad
alias_method :bar, :foo
alias :bar :foo
```
```ruby
# EnforcedStyle: prefer_alias_method

# good
alias_method :bar, :foo

# bad
alias bar foo
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | prefer_alias
SupportedStyles | prefer_alias, prefer_alias_method

## Further Reading

* [RuboCop - Style/Alias](https://docs.rubocop.org/rubocop/cops_style.html#stylealias)
* [https://github.com/bbatsov/ruby-style-guide#alias-method](https://github.com/bbatsov/ruby-style-guide#alias-method)
