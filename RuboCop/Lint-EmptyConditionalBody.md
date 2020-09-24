Pattern: Empty conditional body

Issue: -

## Description

This rule checks for the presence of `if`, `elsif` and `unless` branches without a body.

## Examples

```ruby
# bad
if condition
end

# bad
unless condition
end

# bad
if condition
  do_something
elsif other_condition
end

# good
if condition
  do_something
end

# good
unless condition
  do_something
end

# good
if condition
  do_something
elsif other_condition
  do_something_else
end
```

#### AllowComments: true (default)

```ruby
# good
if condition
  do_something
elsif other_condition
  # noop
end
```

#### AllowComments: false

```ruby
# bad
if condition
  do_something
elsif other_condition
  # noop
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
AllowComments | `true` | Boolean

## Further Reading

* [RuboCop - Lint/EmptyConditionalBody](https://docs.rubocop.org/rubocop/cops_lint.html#lintemptyconditionalbody)
