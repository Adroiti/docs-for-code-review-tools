Pattern: Malformed space around block parameter pipe

Issue: -

## Description

Checks the spacing inside and after block parameters pipes.

## Examples

```ruby
# EnforcedStyleInsidePipes: no_space (default)

# bad
{}.each { | x,  y |puts x }
->( x,  y ) { puts x }

# good
{}.each { |x, y| puts x }
->(x, y) { puts x }
```
```ruby
# EnforcedStyleInsidePipes: space

# bad
{}.each { |x,  y| puts x }
->(x,  y) { puts x }

# good
{}.each { | x, y | puts x }
->( x, y ) { puts x }
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyleInsidePipes | no_space
SupportedStylesInsidePipes | space, no_space

## Further Reading

* [RuboCop - Layout/SpaceAroundBlockParameters](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspacearoundblockparameters)
