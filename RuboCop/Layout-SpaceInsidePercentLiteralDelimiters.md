Pattern: Space inside percent literal delimiters

Issue: -

## Description

Checks for unnecessary additional spaces inside the delimiters of `%i`/`%w`/`%x` literals.

## Examples

```ruby
# good
%i(foo bar baz)

# bad
%w( foo bar baz )

# bad
%x(  ls -l )
```

## Further Reading

* [RuboCop - Layout/SpaceInsidePercentLiteralDelimiters](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutspaceinsidepercentliteraldelimiters)
