Pattern: Missing use of `Rails.root.join`

Issue: -

## Description

This rule is used to identify usages of file path joining process to use `Rails.root.join` clause.

## Examples

```ruby
# bad
Rails.root.join('app/models/goober')
File.join(Rails.root, 'app/models/goober')
"#{Rails.root}/app/models/goober"

# good
Rails.root.join('app', 'models', 'goober')
```

## Further Reading

* [RuboCop - Rails/FilePath](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsfilepath)
