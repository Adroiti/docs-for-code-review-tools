Pattern: Invalid `I18n` method name

Issue: -

## Description

This rule enforces that short forms of `I18n` methods are used: `t` instead of `translate` and `l` instead of `localize`.

This rule has two different enforcement modes. When the EnforcedStyle is conservative (the default) then only `I18n.translate` and `I18n.localize` calls are added as offenses.

When the EnforcedStyle is aggressive then all `translate` and `localize` calls without a receiver are added as offenses.

## Examples

```ruby
# bad
I18n.translate :key
I18n.localize Time.now

# good
I18n.t :key
I18n.l Time.now
```

#### EnforcedStyle: conservative (default)

```ruby
# good
translate :key
localize Time.now
t :key
l Time.now
```

#### EnforcedStyle: aggressive

```ruby
# bad
translate :key
localize Time.now

# good
t :key
l Time.now
```

## Further Reading

* [RuboCop - Rails/ShortI18n](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsshorti18n)
