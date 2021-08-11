Pattern: Inconsistent spec file path

Issue: -

## Description

Checks that spec file paths are consistent with the test subject.

Checks the path of the spec file and enforces that it reflects the
described class/module and its optionally called out method.

With the configuration option `IgnoreMethods` the called out method will
be ignored when determining the enforced path.

With the configuration option `CustomTransform` modules or classes can
be specified that should not as usual be transformed from CamelCase to
snake_case (e.g. 'RuboCop' => 'rubocop' ).

## Examples

```ruby
# bad
whatever_spec.rb         # describe MyClass

# bad
my_class_spec.rb         # describe MyClass, '#method'

# good
my_class_spec.rb         # describe MyClass

# good
my_class_method_spec.rb  # describe MyClass, '#method'

# good
my_class/method_spec.rb  # describe MyClass, '#method'
```
#### when configuration is `IgnoreMethods: true`

```ruby
# bad
whatever_spec.rb         # describe MyClass

# good
my_class_spec.rb         # describe MyClass

# good
my_class_spec.rb         # describe MyClass, '#method'
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
CustomTransform | `{"RuboCop"=>"rubocop", "RSpec"=>"rspec"}` | 
IgnoreMethods | `false` | Boolean

## Further Reading

* [RSpec - RSpec/FilePath](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecfilepath)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/FilePath](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/FilePath)
