Pattern: Redundant heredoc delimiter quotes

Issue: -

## Description

Checks for redundant heredoc delimiter quotes.

## Examples

```ruby
# bad
do_something(<<~'EOS')
  no string interpolation style text
EOS

# good
do_something(<<~EOS)
  no string interpolation style text
EOS

do_something(<<~'EOS')
  #{string_interpolation_style_text_not_evaluated}
EOS

do_something(<<~'EOS')
  Preserve \
  newlines
EOS
```

## Further Reading

* [RuboCop - Style/RedundantHeredocDelimiterQuotes](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantheredocdelimiterquotes)
