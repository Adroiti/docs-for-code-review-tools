Pattern: Malformed heredoc indentation 

Issue: -

## Description

This rule checks the indentation of the here document bodies. The bodies
are indented one step.
In Ruby 2.3 or newer, squiggly heredocs (`<<~`) should be used. If you
use the older rubies, you should introduce some library to your project
(e.g. ActiveSupport, Powerpack or Unindent).

## Examples

```ruby
# bad
<<-RUBY
something
RUBY

# good
# When EnforcedStyle is squiggly
<<~RUBY
  something
RUBY

# good
# When EnforcedStyle is active_support
<<-RUBY.strip_heredoc
  something
RUBY
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | auto_detection
SupportedStyles | auto_detection, squiggly, active_support, powerpack, unindent

## Further Reading

* [RuboCop - Layout/IndentHeredoc](https://docs.rubocop.org/rubocop/cops_layout.html#layoutindentheredoc)
* [https://github.com/bbatsov/ruby-style-guide#squiggly-heredocs](https://github.com/bbatsov/ruby-style-guide#squiggly-heredocs)
