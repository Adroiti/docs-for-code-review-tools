Pattern: Misuse of date-aware method

Issue: -

## Description

This rule checks for the correct use of Date methods,
such as `Date.today`, `Date.current` etc.

Using `Date.today` is dangerous, because it doesn't know anything about
Rails time zone. You should use `Time.zone.today` instead.

The rule also reports warnings when you are using `to_time` method,
because it doesn't know about Rails time zone either.

Two styles are supported for this rule. When _EnforcedStyle_ is `strict`
then the Date methods (`today`, `current`, `yesterday`, `tomorrow`)
are prohibited and the usage of both `to_time`
and `to_time_in_current_zone` is reported as warning.

When _EnforcedStyle_ is `flexible` then only `Date.today` is prohibited
and only `to_time` is reported as warning.

## Examples

```ruby
# no offense
Time.zone.today
Time.zone.today - 1.day

# flexible
Date.current
Date.yesterday

# always reports offense
Date.today
date.to_time

# reports offense only when style is 'strict'
date.to_time_in_current_zone
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | flexible
SupportedStyles | strict, flexible

## Further Reading

* [RuboCop - Rails/Date](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsdate)
