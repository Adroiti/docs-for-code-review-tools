Pattern: Inconsistent use of `request.referer`/`request.referrer`

Issue: -

## Description

This cop checks for consistent uses of `request.referer` or `request.referrer`, depending on the cop's configuration.

### Example

```ruby
# EnforcedStyle: referer
# bad
request.referrer

# good
request.referer

# EnforcedStyle: referrer
# bad
request.referer

# good
request.referrer
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | referer
SupportedStyles | referer, referrer

## Further Reading

* [RuboCop - Rails/RequestReferer](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsrequestreferer)
