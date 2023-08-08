Pattern: Missing `` or `%x` around command literal

Issue: -

## Description

This rule enforces using `` or `%x` around command literals.

## Examples

```ruby
# Good if EnforcedStyle is backticks or mixed, bad if percent_x.
folders = `find . -type d`.split

# Good if EnforcedStyle is percent_x, bad if backticks or mixed.
folders = %x(find . -type d).split

# Good if EnforcedStyle is backticks, bad if percent_x or mixed.
`
  ln -s foo.example.yml foo.example
  ln -s bar.example.yml bar.example
`

# Good if EnforcedStyle is percent_x or mixed, bad if backticks.
%x(
  ln -s foo.example.yml foo.example
  ln -s bar.example.yml bar.example
)

# Bad unless AllowInnerBackticks is true.
`echo \`ls\``
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | backticks
SupportedStyles | backticks, percent_x, mixed
AllowInnerBackticks | false

## Further Reading

* [RuboCop - Style/CommandLiteral](https://docs.rubocop.org/rubocop/cops_style.html#stylecommandliteral)
* [https://github.com/bbatsov/ruby-style-guide#percent-x](https://github.com/bbatsov/ruby-style-guide#percent-x)
