Pattern: Redundant Regexp constructor

Issue: -

## Description

Checks for the instantiation of Regexp using redundant `Regexp.new` or `Regexp.compile`.
Autocorrect replaces to Regexp literal which is the simplest and fastest.

## Examples

```ruby
# bad
Regexp.new(/regexp/)
Regexp.compile(/regexp/)

# good
/regexp/
Regexp.new('regexp')
Regexp.compile('regexp')
```

## Further Reading

* [RuboCop - Style/RedundantRegexpConstructor](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantregexpconstructor)
