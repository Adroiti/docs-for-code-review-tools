Pattern: Malformed source file encoding

Issue: -

## Description

This rule checks whether the source file has a `UTF-8` encoding
comment or not.
Setting this check to `always` and `when_needed` makes sense only
for code that should support Ruby 1.9, since in 2.0+ `UTF-8` is the
default source file encoding. There are three styles:

when_needed - only enforce an encoding comment if there are non ASCII
              characters, otherwise report an offense
always - enforce encoding comment in all files
never - enforce no encoding comment in all files

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | never
SupportedStyles | when_needed, always, never

## Further Reading

* [RuboCop - Style/Encoding](https://docs.rubocop.org/rubocop/cops_style.html#styleencoding)
* [https://github.com/bbatsov/ruby-style-guide#utf-8](https://github.com/bbatsov/ruby-style-guide#utf-8)
