Pattern: Space inside array percent literal

Issue: -

## Description

Checks for unnecessary additional spaces inside array percent literals (i.e. `%i`/`%w`).

## Examples

```ruby
# good
%i(foo bar baz)

# bad
%w(foo  bar  baz)
```

## Further Reading

* [RuboCop - Layout/SpaceInsideArrayPercentLiteral](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspaceinsidearraypercentliteral)
