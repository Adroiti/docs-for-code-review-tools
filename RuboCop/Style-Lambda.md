Pattern: Inconsistent lambda literal syntax

Issue: -

## Description

This rule (by default) checks for uses of the lambda literal syntax for
single line lambdas, and the method call syntax for multi-line lambdas.
It is configurable to enforce one of the styles for both single line
and multi-line lambdas as well.

## Examples

```ruby
# EnforcedStyle: line_count_dependent (default)

# bad
f = lambda { |x| x }
f = ->(x) do
      x
    end

# good
f = ->(x) { x }
f = lambda do |x|
      x
    end
```
```ruby
# EnforcedStyle: lambda

# bad
f = ->(x) { x }
f = ->(x) do
      x
    end

# good
f = lambda { |x| x }
f = lambda do |x|
      x
    end
```
```ruby
# EnforcedStyle: literal

# bad
f = lambda { |x| x }
f = lambda do |x|
      x
    end

# good
f = ->(x) { x }
f = ->(x) do
      x
    end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | line_count_dependent
SupportedStyles | line_count_dependent, lambda, literal

## Further Reading

* [RuboCop - Style/Lambda](https://rubocop.readthedocs.io/en/latest/cops_style/#stylelambda)
* [https://github.com/bbatsov/ruby-style-guide#lambda-multi-line](https://github.com/bbatsov/ruby-style-guide#lambda-multi-line)
