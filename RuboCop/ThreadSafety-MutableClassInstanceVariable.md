Pattern: Use of mutable class instance variable

Issue: -

## Description

This cop checks whether some class instance variable isn't a
mutable literal (e.g. array or hash).

Class instance variables are a risk to threaded code as they are shared
between threads.

Strict mode can be used to freeze all class instance variables, rather
than just literals.
Strict mode is considered an experimental feature. It has not been
updated with an exhaustive list of all methods that will produce frozen
objects so there is a decent chance of getting some false positives.
Luckily, there is no harm in freezing an already frozen object.

## Examples

```ruby
@example EnforcedStyle: literals (default)
  # bad
  class Model
    @list = [1, 2, 3]
  end

  # good
  class Model
    @list = [1, 2, 3].freeze
  end

  # good
  class Model
    @var = <<~TESTING.freeze
      This is a heredoc
    TESTING
  end

  # good
  class Model
    @var = Something.new
  end

@example EnforcedStyle: strict
  # bad
  class Model
    @var = Something.new
  end

  # bad
  class Model
    @var = Struct.new do
      def foo
        puts 1
      end
    end
  end

  # good
  class Model
    @var = Something.new.freeze
  end

  # good
  class Model
    @var = Struct.new do
      def foo
        puts 1
      end
    end.freeze
  end
```

## Further Reading

* [RuboCop - ThreadSafety/MutableClassInstanceVariable](https://github.com/covermymeds/rubocop-thread_safety/blob/master/lib/rubocop/cop/thread_safety/mutable_class_instance_variable.rb)
