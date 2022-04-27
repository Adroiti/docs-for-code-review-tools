Pattern: Use of `ENV[]` instead of `ENV.fetch`

Issue: -

## Description

This rule suggests `ENV.fetch` for the replacement of `ENV[]`.
`ENV[]` silently fails and returns `nil` when the environment variable is unset,
which may cause unexpected behaviors when the developer forgets to set it.
On the other hand, `ENV.fetch` raises KeyError or returns the explicitly
specified default value.

## Examples

```ruby
# bad
ENV['X']
ENV['X'] || z
x = ENV['X']

# good
ENV.fetch('X')
ENV.fetch('X', nil) || z
x = ENV.fetch('X')

# also good
!ENV['X']
ENV['X'].some_method # (e.g. `.nil?`)
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
AllowedVars | `[]` | Array

## Further Reading

* [RuboCop - Style/FetchEnvVar](https://docs.rubocop.org/rubocop/cops_style.html#stylefetchenvvar)