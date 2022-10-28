Pattern: Use of deprecated `HashWithIndifferentAccess`

Issue: -

## Description

Identifies top-level `HashWithIndifferentAccess`.
This has been soft-deprecated since Rails 5.1.

## Examples

```ruby
# bad
HashWithIndifferentAccess.new(foo: 'bar')

# good
ActiveSupport::HashWithIndifferentAccess.new(foo: 'bar')
```

## Further Reading

* [Rails - Rails/TopLevelHashWithIndifferentAccess](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railstoplevelhashwithindifferentaccess)
* https://guides.rubyonrails.org/upgrading_ruby_on_rails.html#top-level-hashwithindifferentaccess-is-soft-deprecated