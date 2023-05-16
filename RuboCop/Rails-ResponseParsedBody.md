Pattern: Missing use of `response.parsed_body`

Issue: -

## Description

Prefer `response.parsed_body` to `JSON.parse(response.body)`.

This rule is unsafe because Content-Type may not be `application/json`. For example, the proprietary
Content-Type provided by corporate entities such as `application/vnd.github+json` is not supported at
`response.parsed_body` by default, so you still have to use `JSON.parse(response.body)` there.

## Examples

```ruby
# bad
JSON.parse(response.body)

# good
response.parsed_body
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Include | `+spec/controllers/**/*.rb+`, `+spec/requests/**/*.rb+`, `+test/controllers/**/*.rb+`, `+test/integration/**/*.rb+` | Array

## Further Reading

* [Rails - Rails/ResponseParsedBody](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsresponseparsedbody)
