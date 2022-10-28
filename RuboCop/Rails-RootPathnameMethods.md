Pattern: Missing use of `Rails.root` IO method

Issue: -

## Description

Use `Rails.root` IO methods instead of passing it to `File`.

`Rails.root` is an instance of `Pathname` so we can apply many IO methods directly.

This rule works best when used together with `Style/FileRead`, `Style/FileWrite` and `Rails/RootJoinChain`.

## Examples

```ruby
# bad
File.open(Rails.root.join('db', 'schema.rb'))
File.open(Rails.root.join('db', 'schema.rb'), 'w')
File.read(Rails.root.join('db', 'schema.rb'))
File.binread(Rails.root.join('db', 'schema.rb'))
File.write(Rails.root.join('db', 'schema.rb'), content)
File.binwrite(Rails.root.join('db', 'schema.rb'), content)

# good
Rails.root.join('db', 'schema.rb').open
Rails.root.join('db', 'schema.rb').open('w')
Rails.root.join('db', 'schema.rb').read
Rails.root.join('db', 'schema.rb').binread
Rails.root.join('db', 'schema.rb').write(content)
Rails.root.join('db', 'schema.rb').binwrite(content)
```
## Further Reading

* [Rails - Rails/RootPathnameMethods](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsrootpathnamemethods)
