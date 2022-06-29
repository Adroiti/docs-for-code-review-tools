Pattern: Constant overwritten in `rescue`

Issue: -

## Description

Checks for overwriting an exception with an exception result by using `rescue ⇒`.

You intended to write as `rescue StandardError`. However, you have written `rescue ⇒ StandardError`. In that case, the result of rescue will overwrite `StandardError`.

## Examples

```ruby
# bad
begin
  something
rescue => StandardError
end

# good
begin
  something
rescue StandardError
end
```

## Further Reading

* [RuboCop - Lint/ConstantOverwrittenInRescue](https://docs.rubocop.org/rubocop/cops_lint.html#lintconstantoverwritteninrescue)
