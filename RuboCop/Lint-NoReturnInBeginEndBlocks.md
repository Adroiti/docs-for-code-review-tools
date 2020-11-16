Pattern: Use of `return` inside `begin..end`

Issue: -

## Description

Checks for the presence of a `return` inside a `begin..end` block in assignment contexts. In this situation, the `return` will result in an exit from the current method, possibly leading to unexpected behavior.

## Examples

```ruby
# bad

@some_variable ||= begin
  return some_value if some_condition_is_met

  do_something
end


# good

@some_variable ||= begin
  if some_condition_is_met
    some_value
  else
    do_something
  end
end

# good

some_variable = if some_condition_is_met
                  return if another_condition_is_met

                  some_value
                else
                  do_something
                end
```

## Further Reading

* [RuboCop - Lint/NoReturnInBeginEndBlocks](https://docs.rubocop.org/rubocop/cops_lint.html#lintnoreturninbeginendblocks)
