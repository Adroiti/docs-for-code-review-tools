Pattern: Misused `File.expand_path`/`Pathname.new`

Issue: -

## Description

This rule checks for use of the `File.expand_path` arguments.
Likewise, it also checks for the `Pathname.new` argument.

Contrastive bad case and good case are alternately shown in
the following examples.

## Examples

```ruby
# bad
File.expand_path('..', __FILE__)

# good
File.expand_path(__dir__)

# bad
File.expand_path('../..', __FILE__)

# good
File.expand_path('..', __dir__)

# bad
File.expand_path('.', __FILE__)

# good
File.expand_path(__FILE__)

# bad
Pathname(__FILE__).parent.expand_path

# good
Pathname(__dir__).expand_path

# bad
Pathname.new(__FILE__).parent.expand_path

# good
Pathname.new(__dir__).expand_path
```

## Further Reading

* [RuboCop - Style/ExpandPathArguments](https://rubocop.readthedocs.io/en/latest/cops_style/#styleexpandpatharguments)
