Pattern: Redundant `sort` for `Dir.glob`/`Dir[]`

Issue: -

## Description

This rule checks for redundant `sort` method to `Dir.glob` and `Dir[]`.

## Examples

```ruby
# bad
Dir.glob('./lib/**/*.rb').sort.each do |file|
end

Dir['./lib/**/*.rb'].sort.each do |file|
end

# good
Dir.glob('./lib/**/*.rb').each do |file|
end

Dir['./lib/**/*.rb'].each do |file|
end
```

## Further Reading

* [RuboCop - Lint/RedundantDirGlobSort](https://docs.rubocop.org/rubocop/cops_lint.html#lintredundantdirglobsort)
