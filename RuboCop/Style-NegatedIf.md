Pattern: `if` with negated condition

Issue: -

## Description

Checks for uses of `if` with a negated condition. Only `if`s without `else` are considered. There are three different styles:

  - both
  - prefix
  - postfix

### Example

```ruby
# EnforcedStyle: both
# enforces `unless` for `prefix` and `postfix` conditionals

# good

unless foo
  bar
end

# bad

if !foo
  bar
end

# good

bar unless foo

# bad

bar if !foo
```
```ruby
# EnforcedStyle: prefix
# enforces `unless` for just `prefix` conditionals

# good

unless foo
  bar
end

# bad

if !foo
  bar
end

# good

bar if !foo
```
```ruby
# EnforcedStyle: postfix
# enforces `unless` for just `postfix` conditionals

# good

bar unless foo

# bad

bar if !foo

# good

if !foo
  bar
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | both
SupportedStyles | both, prefix, postfix

## Further Reading

* [RuboCop - Style/NegatedIf](https://rubocop.readthedocs.io/en/latest/cops_style/#stylenegatedif)
* [https://github.com/bbatsov/ruby-style-guide#unless-for-negatives](https://github.com/bbatsov/ruby-style-guide#unless-for-negatives)
