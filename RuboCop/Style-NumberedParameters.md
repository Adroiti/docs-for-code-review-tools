Pattern: Malformed numbered parameters

Issue: -

## Description

This rule checks for numbered parameters.

It can either restrict the use of numbered parameters to
single-lined blocks, or disallow completely numbered parameters.

## Examples

#### EnforcedStyle: allow_single_line (default)

```ruby
# bad
collection.each do
  puts _1
end

# good
collection.each { puts _1 }
```

#### EnforcedStyle: disallow

```ruby
# bad
collection.each { puts _1 }

# good
collection.each { |item| puts item }
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `allow_single_line` | `allow_single_line`, `disallow`

## Further Reading

* [RuboCop - Style/NumberedParameters](https://docs.rubocop.org/rubocop/cops_style.html#stylenumberedparameters)
