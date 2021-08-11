Pattern: Missing use of `expect { ... }.to output`

Issue: -

## Description

Checks for opportunities to use `expect { ... }.to output`.

## Examples

```ruby
# bad
$stdout = StringIO.new
my_app.print_report
$stdout = STDOUT
expect($stdout.string).to eq('Hello World')

# good
expect { my_app.print_report }.to output('Hello World').to_stdout
```

## Further Reading

* [RSpec - RSpec/ExpectOutput](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecexpectoutput)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExpectOutput](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExpectOutput)
