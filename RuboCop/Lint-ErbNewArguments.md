Pattern: Misuse of `ERB.new`

Issue: -

## Description

Now non-keyword arguments other than first one are softly deprecated
and will be removed when Ruby 2.5 becomes EOL.
`ERB.new` with non-keyword arguments is deprecated since ERB 2.2.0.
Use `:trim_mode` and `:eoutvar` keyword arguments to `ERB.new`.
This rule identifies places where `ERB.new(str, trim_mode, eoutvar)` can
be replaced by `ERB.new(str, :trim_mode: trim_mode, eoutvar: eoutvar)`.

## Examples

```ruby
# Target codes supports Ruby 2.6 and higher only
# bad
ERB.new(str, nil, '-', '@output_buffer')

# good
ERB.new(str, trim_mode: '-', eoutvar: '@output_buffer')

# Target codes supports Ruby 2.5 and lower only
# good
ERB.new(str, nil, '-', '@output_buffer')

# Target codes supports Ruby 2.6, 2.5 and lower
# bad
ERB.new(str, nil, '-', '@output_buffer')

# good
# Ruby standard library style
# https://github.com/ruby/ruby/commit/3406c5d
if ERB.instance_method(:initialize).parameters.assoc(:key) # Ruby 2.6+
  ERB.new(str, trim_mode: '-', eoutvar: '@output_buffer')
else
  ERB.new(str, nil, '-', '@output_buffer')
end

# good
# Use `RUBY_VERSION` style
if RUBY_VERSION >= '2.6'
  ERB.new(str, trim_mode: '-', eoutvar: '@output_buffer')
else
  ERB.new(str, nil, '-', '@output_buffer')
end
```

## Further Reading

* [RuboCop - Lint/ErbNewArguments](https://docs.rubocop.org/rubocop/cops_lint.html#linterbnewarguments)
