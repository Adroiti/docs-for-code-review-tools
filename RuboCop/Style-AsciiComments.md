Pattern: Non-English comment

Issue: -

## Description

This rule checks for non-ascii (non-English) characters in comments.

## Examples

```ruby
# bad
# Translates from English to 日本語。

# good
# Translates from English to Japanese
```

## Default configuration

Attribute | Value
--- | ---
AllowedChars | `[]`

## Further Reading

* [RuboCop - Style/AsciiComments](https://rubocop.readthedocs.io/en/latest/cops_style/#styleasciicomments)
* [https://github.com/bbatsov/ruby-style-guide#english-comments](https://github.com/bbatsov/ruby-style-guide#english-comments)
