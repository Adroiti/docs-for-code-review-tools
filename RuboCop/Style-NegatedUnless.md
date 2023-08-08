Pattern: Misused `unless` with negated condition

Issue: -

## Description

Checks for uses of `unless` with a negated condition. Only `unless` without `else` are considered. There are three different styles:

  - both
  - prefix
  - postfix

## Examples

#### EnforcedStyle: both (default)

```ruby
# enforces `if` for `prefix` and `postfix` conditionals

# bad
unless !foo
  bar
end

# good
if foo
  bar
end

# bad
bar unless !foo

# good
bar if foo
```
#### EnforcedStyle: prefix

```ruby
# enforces `if` for just `prefix` conditionals

# bad
unless !foo
  bar
end

# good
if foo
  bar
end

# good
bar unless !foo
```
#### EnforcedStyle: postfix

```ruby
# enforces `if` for just `postfix` conditionals

# bad
bar unless !foo

# good
bar if foo

# good
unless !foo
  bar
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `both` | `both`, `prefix`, `postfix`

## Further Reading

* [RuboCop - Style/NegatedUnless](https://docs.rubocop.org/rubocop/cops_style.html#stylenegatedunless)
* [https://rubystyle.guide#if-for-negatives](https://rubystyle.guide#if-for-negatives)
