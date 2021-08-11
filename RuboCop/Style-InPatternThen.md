Pattern: Use of `in;` in `case` 

Issue: -

## Description

Checks for `in;` uses in `case` expressions.

## Examples

```ruby
# bad
case expression
in pattern_a; foo
in pattern_b; bar
end

# good
case expression
in pattern_a then foo
in pattern_b then bar
end
```

## Further Reading

* [RuboCop - Style/InPatternThen](https://docs.rubocop.org/rubocop/cops_style.html#styleinpatternthen)