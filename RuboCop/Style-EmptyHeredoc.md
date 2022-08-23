Pattern: Empty heredoc

Issue: -

## Description

Checks for using empty heredoc to reduce redundancy.

## Examples

```ruby
# bad
<<~EOS
EOS

<<-EOS
EOS

<<EOS
EOS

# good
''

# bad
do_something(<<~EOS)
EOS

do_something(<<-EOS)
EOS

do_something(<<EOS)
EOS

# good
do_something('')
```

## Further Reading

* [RuboCop - Style/EmptyHeredoc](https://docs.rubocop.org/rubocop/cops_style.html#styleemptyheredoc)
