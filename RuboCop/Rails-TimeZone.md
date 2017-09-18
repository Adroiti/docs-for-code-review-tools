Pattern: Use of `Time` method without zone

Issue: -

## Description

This rule checks for the use of `Time` methods without zone.

Two styles are supported for this rule. When _EnforcedStyle_ is `strict`
then only use of `Time.zone` is allowed.

When _EnforcedStyle_ is `flexible` then it's also allowed
to use `Time.in_time_zone`.

## Examples

```ruby
# always offense
Time.now
Time.parse('2015-03-02 19:05:37')

# no offense
Time.zone.now
Time.zone.parse('2015-03-02 19:05:37')

# no offense only if style is 'flexible'
Time.current
DateTime.strptime(str, "%Y-%m-%d %H:%M %Z").in_time_zone
Time.at(timestamp).in_time_zone
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | flexible
SupportedStyles | strict, flexible

## Further Reading

* [RuboCop - Rails/TimeZone](https://rubocop.readthedocs.io/en/latest/cops_rails/#railstimezone)
* [https://github.com/bbatsov/rails-style-guide#time](https://github.com/bbatsov/rails-style-guide#time)
* [http://danilenko.org/2012/7/6/rails_timezones](http://danilenko.org/2012/7/6/rails_timezones)
