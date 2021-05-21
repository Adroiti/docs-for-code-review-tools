Pattern: Use of instance variable in class method

Issue: -

## Description

Avoid instance variables in class methods.

## Examples

```ruby
# bad
class User
  def self.notify(info)
    @info = validate(info)
    Notifier.new(@info).deliver
  end
end

class Model
  class << self
    def table_name(name)
      @table_name = name
    end
  end
end

class Host
  %i[uri port].each do |key|
    define_singleton_method("#{key}=") do |value|
      instance_variable_set("@#{key}", value)
    end
  end
end

module Example
  module ClassMethods
    def test(params)
      @params = params
    end
  end
end
```

## Further Reading

* [RuboCop - ThreadSafety/InstanceVariableInClassMethod](https://github.com/covermymeds/rubocop-thread_safety/blob/master/lib/rubocop/cop/thread_safety/instance_variable_in_class_method.rb)
