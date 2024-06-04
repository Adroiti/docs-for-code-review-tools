Pattern: Missing use of `map`

Issue: -

## Description

Checks for usages of `each` with `<<`, `push`, or `append` which can be replaced by `map`.

If `PreferredMethods` is configured for map in `Style/CollectionMethods`, this cop uses the specified method for replacement.

## Examples

```ruby
# bad
dest = []
src.each { |e| dest << e * 2 }
dest

# good
dest = src.map { |e| e * 2 }

# good - contains another operation
dest = []
src.each { |e| dest << e * 2; puts e }
dest
```

## Further Reading

* [RuboCop - Style/MapIntoArray](https://docs.rubocop.org/rubocop/cops_style.html#stylemapintoarray)