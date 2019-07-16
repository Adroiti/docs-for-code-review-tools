Pattern: Use of method that skips model validation

Issue: -

## Description

This rule checks for the use of methods which skip model validation.

## Examples

```ruby
# bad
Article.first.decrement!(:view_count)
DiscussionBoard.decrement_counter(:post_count, 5)
Article.first.increment!(:view_count)
DiscussionBoard.increment_counter(:post_count, 5)
person.toggle :active
product.touch
Billing.update_all("category = 'authorized', author = 'David'")
user.update_attribute(website: 'example.com')
user.update_columns(last_request_at: Time.current)
Post.update_counters 5, comment_count: -1, action_count: 1

# good
user.update_attributes(website: 'example.com')
FileUtils.touch('file')
```

## Default configuration

Attribute | Value
--- | ---
Blacklist | decrement!, decrement_counter, increment!, increment_counter, toggle!, touch, update_all, update_attribute, update_column, update_columns, update_counters

## Further Reading

* [RuboCop - Rails/SkipsModelValidations](https://github.com/rubocop-hq/rubocop-rails/tree/master/lib/rubocop/cop/rails#railsskipsmodelvalidations)
* [http://guides.rubyonrails.org/active_record_validations.html#skipping-validations](http://guides.rubyonrails.org/active_record_validations.html#skipping-validations)
