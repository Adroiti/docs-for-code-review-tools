Pattern: Redundant `:foreign_key` option

Issue: -

## Description

Checks for associations where the `:foreign_key` option is redundant.

## Examples

```ruby
# bad
class Post
  has_many :comments, foreign_key: 'post_id'
end

class Comment
  belongs_to :post, foreign_key: 'post_id'
end

# good
class Post
  has_many :comments
end

class Comment
  belongs_to :author, foreign_key: 'user_id'
end
```

## Further Reading

* [RuboCop - Rails/RedundantForeignKey](https://github.com/eugeneius/rubocop-rails/blob/45cbda4d1806179f714d1090ab61c5512d8ff3b2/docs/modules/ROOT/pages/cops_rails.adoc#railsredundantforeignkey)
