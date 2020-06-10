Pattern: Use of legacy `content_tag`

Issue: -

## Description

Checks that `tag` is used instead of `content_tag` because `content_tag` is legacy syntax.

## Examples

```ruby
# bad
content_tag(:p, 'Hello world!')
content_tag(:br)

# good
tag.p('Hello world!')
tag.br
content_tag(name, 'Hello world!')
```

## Further Reading

* [RuboCop - Rails/ContentTag](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railscontenttag)
