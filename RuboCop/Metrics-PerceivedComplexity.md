Pattern: Perceived complexity is too high

Issue: -

## Description

This rule tries to produce a complexity score that's a measure of the
complexity the reader experiences when looking at a method. For that
reason it considers `when` nodes as something that doesn't add as much
complexity as an `if` or a `&&`. Except if it's one of those special
`case`/`when` constructs where there's no expression after `case`. Then
the rule treats it as an `if`/`elsif`/`elsif`... and lets all the `when`
nodes count. This rule considers `else` nodes as adding complexity.

## Examples

```ruby
def my_method                   # 1
  if cond                       # 1
    case var                    # 2 (0.8 + 4 * 0.2, rounded)
    when 1 then func_one
    when 2 then func_two
    when 3 then func_three
    when 4..10 then func_other
    end
  else                          # 1
    do_something until a && b   # 2
  end                           # ===
end                             # 7 complexity points
```

## Default configuration

Attribute | Value
--- | ---
Max | 7

## Further Reading

* [RuboCop - Metrics/PerceivedComplexity](https://docs.rubocop.org/rubocop/cops_metrics.html#metricsperceivedcomplexity)
