Pattern: Use of `describe`/`context` under namespace

Issue: -

## Description

Checks for Rspec `describe` or `context` method calls under a namespace. It can potentially cause autoloading to occur in a different order than it would have in development or production. This could cause flaky tests.

## Examples

```ruby
# bad

# spec/foo/bar_spec.rb
module Foo
  describe Bar do
  end
end

# good

# spec/foo/bar_spec.rb do

describe Foo::Bar
end
```

## Further Reading

* [RuboCop - Airbnb/RspecDescribeOrContextUnderNamespace](https://github.com/airbnb/ruby/blob/master/rubocop-airbnb/lib/rubocop/cop/airbnb/rspec_describe_or_context_under_namespace.rb)
