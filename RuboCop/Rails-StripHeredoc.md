Pattern: Use of `strip_heredoc`

Issue: -

## Description

Enforces the use of squiggly heredoc over `strip_heredoc`.

## Examples

```ruby
# bad
<<EOS.strip_heredoc
  some text
EOS

# bad
<<-EOS.strip_heredoc
  some text
EOS

# good
<<~EOS
  some text
EOS
```

## Further Reading

* [Rails - Rails/StripHeredoc](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsstripheredoc)
* https://rails.rubystyle.guide/#prefer-squiggly-heredoc