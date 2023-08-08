Pattern: Redundant Regexp argument

Issue: -

## Description

Identifies places where argument can be replaced from
a deterministic Regexp to a string.

## Examples

```ruby
# bad
'foo'.byteindex(/f/)
'foo'.byterindex(/f/)
'foo'.gsub(/f/, 'x')
'foo'.gsub!(/f/, 'x')
'foo'.partition(/f/)
'foo'.rpartition(/f/)
'foo'.scan(/f/)
'foo'.split(/f/)
'foo'.start_with?(/f/)
'foo'.sub(/f/, 'x')
'foo'.sub!(/f/, 'x')

# good
'foo'.byteindex('f')
'foo'.byterindex('f')
'foo'.gsub('f', 'x')
'foo'.gsub!('f', 'x')
'foo'.partition('f')
'foo'.rpartition('f')
'foo'.scan('f')
'foo'.split('f')
'foo'.start_with?('f')
'foo'.sub('f', 'x')
'foo'.sub!('f', 'x')
```

## Further Reading

* [RuboCop - Style/RedundantRegexpArgument](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantregexpargument)
