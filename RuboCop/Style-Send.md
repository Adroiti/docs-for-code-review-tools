Pattern: Use of `send` method

Issue: -

## Description

Prefer `public_send` over `send` so as not to circumvent `private`/`protected` visibility. 

## Examples

```ruby
# An ActiveModel Organization that includes concern Activatable
module Activatable
  extend ActiveSupport::Concern

  included do
    before_create :create_token
  end

  private

  def reset_token
    # some code
  end

  def create_token
    # some code
  end

  def activate!
    # some code
  end
end

class Organization < ActiveRecord::Base
  include Activatable
end

linux_organization = Organization.find(...)
# BAD - violates privacy
linux_organization.send(:reset_token)
# GOOD - should throw an exception
linux_organization.public_send(:reset_token)
```

## Further Reading

* [RuboCop - Style/Send](https://docs.rubocop.org/rubocop/cops_style.html#stylesend)
* [https://github.com/bbatsov/ruby-style-guide#prefer-public-send](https://github.com/bbatsov/ruby-style-guide#prefer-public-send)
