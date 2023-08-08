Pattern: Misaligned arguments for multi-line method

Issue: -

## Description

Checks if the arguments on a multi-line method definition are aligned.

## Examples

#### EnforcedStyle: with_first_argument (default)

```ruby
# good

foo :bar,
    :baz

foo(
  :bar,
  :baz
)

# bad

foo :bar,
  :baz

foo(
  :bar,
    :baz
)
```
#### EnforcedStyle: with_fixed_indentation

```ruby
# good

foo :bar,
  :baz

# bad

foo :bar,
    :baz
```

## Configurable attributes

Name | Default value
--- | ---
EnforcedStyle | `with_first_argument`
IndentationWidth | `<none>`

## Further Reading

* [RuboCop - Layout/ArgumentAlignment](https://docs.rubocop.org/rubocop/cops_layout.html#layoutargumentalignment)
* [https://github.com/rubocop-hq/ruby-style-guide#no-double-indent](https://github.com/rubocop-hq/ruby-style-guide#no-double-indent)
