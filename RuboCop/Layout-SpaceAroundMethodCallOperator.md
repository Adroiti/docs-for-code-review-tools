Pattern: Use of space around method call operator

Issue: -

## Description

Checks method call operators to not have spaces around them.

## Examples

```ruby
# bad
foo. bar
foo .bar
foo . bar
foo. bar .buzz
foo
  . bar
  . buzz
foo&. bar
foo &.bar
foo &. bar
foo &. bar&. buzz
RuboCop:: Cop
RuboCop:: Cop:: Cop
:: RuboCop::Cop

# good
foo.bar
foo.bar.buzz
foo
  .bar
  .buzz
foo&.bar
foo&.bar&.buzz
RuboCop::Cop
RuboCop::Cop::Cop
::RuboCop::Cop
```

## Further Reading

* [RuboCop - Layout/SpaceAroundMethodCallOperator](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspacearoundmethodcalloperator)
