Pattern: Empty file

Issue: -

## Description

This rule enforces that Ruby source files are not empty.

## Examples

```ruby
# bad
# Empty file

# good
# File containing non commented source lines
```

#### AllowComments: true (default)

```ruby
# good
# File consisting only of comments
```

#### AllowComments: false

```ruby
# bad
# File consisting only of comments
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
AllowComments | `true` | Boolean

## Further Reading

* [RuboCop - Lint/EmptyFile](https://docs.rubocop.org/rubocop/cops_lint.html#lintemptyfile)
