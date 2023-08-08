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

* [RuboCop - Layout/SpaceInsidePercentLiteralDelimiters](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspaceinsidepercentliteraldelimiters)
