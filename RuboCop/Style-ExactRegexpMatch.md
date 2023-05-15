Pattern: Exact regexp match

Issue: -

## Description

Checks for exact regexp match inside Regexp literals.

## Examples

```ruby
# bad
string =~ /\Astring\z/
string === /\Astring\z/
string.match(/\Astring\z/)
string.match?(/\Astring\z/)

# good
string == 'string'

# bad
string !~ /\Astring\z/

# good
string != 'string'
```

## Further Reading

* [RuboCop - Style/ExactRegexpMatch](https://docs.rubocop.org/rubocop/cops_style.html#styleexactregexpmatch)
