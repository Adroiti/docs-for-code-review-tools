Pattern: Malformed `context` block description

Issue: -

## Description

`context` block descriptions should start with 'when', or 'with'.

'without'
  Prefixes:
    - when
    - with
    - without
    - if

## Examples

#### `Prefixes` configuration option, defaults: 'when', 'with', and

```ruby

```
```ruby
# bad
context 'the display name not present' do
  # ...
end

# good
context 'when the display name is not present' do
  # ...
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Prefixes | `when`, `with`, `without` | Array

## Further Reading

* [RSpec - RSpec/ContextWording](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspeccontextwording)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ContextWording](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ContextWording)
