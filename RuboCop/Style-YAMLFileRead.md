Pattern: Use of `File.read` with `YAML`

Issue: -

## Description

Checks for the use of `YAML.load`, `YAML.safe_load`, and `YAML.parse` with
`File.read` argument.

NOTE: `YAML.safe_load_file` was introduced in Ruby 3.0.

## Examples

```ruby
# bad
YAML.load(File.read(path))
YAML.parse(File.read(path))

# good
YAML.load_file(path)
YAML.parse_file(path)

# bad
YAML.safe_load(File.read(path)) # Ruby 3.0 and newer

# good
YAML.safe_load_file(path)       # Ruby 3.0 and newer
```

## Further Reading

* [RuboCop - Style/YAMLFileRead](https://docs.rubocop.org/rubocop/cops_style.html#styleyamlfileread)
