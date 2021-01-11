Pattern: Lambda without literal block

Issue: -

## Description

This rule checks uses of lambda without a literal block.

## Examples

```ruby
# bad
lambda(&proc { do_something })
lambda(&Proc.new { do_something })

# good
proc { do_something }
Proc.new { do_something }
lambda { do_something } # If you use lambda.
```

## Further Reading

* [RuboCop - Lint/LambdaWithoutLiteralBlock](https://docs.rubocop.org/rubocop/cops_lint.html#lintlambdawithoutliteralblock)
