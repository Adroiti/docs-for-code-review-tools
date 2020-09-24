Pattern: Malformed `Mailer` name

Issue: -

## Description

This rule enforces that mailer names end with `Mailer` suffix.

Without the `Mailer` suffix it isn’t immediately apparent what’s a mailer and which views are related to the mailer.

## Examples

```ruby
# bad
class User < ActionMailer::Base
end

class User < ApplicationMailer
end

# good
class UserMailer < ActionMailer::Base
end

class UserMailer < ApplicationMailer
end
```

## Further Reading

* [RuboCop - Rails/MailerName](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsmailername)
