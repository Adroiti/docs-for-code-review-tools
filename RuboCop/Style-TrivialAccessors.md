Pattern: Use of trivial reader/writer

Issue: -

## Description

This rule looks for trivial reader/writer methods, that could
have been created with the attr_* family of functions automatically.

## Examples

```ruby
# bad
class Person
  def initialize(first_name, last_name)
    @first_name = first_name
    @last_name = last_name
  end

  def first_name
    @first_name
  end

  def last_name
    @last_name
  end
end

# good
class Person
  attr_reader :first_name, :last_name

  def initialize(first_name, last_name)
    @first_name = first_name
    @last_name = last_name
  end
end
```

## Default configuration

Attribute | Value
--- | ---
ExactNameMatch | true
AllowPredicates | true
AllowDSLWriters | false
IgnoreClassMethods | false
Whitelist | to_ary, to_a, to_c, to_enum, to_h, to_hash, to_i, to_int, to_io, to_open, to_path, to_proc, to_r, to_regexp, to_str, to_s, to_sym

## Further Reading

* [RuboCop - Style/TrivialAccessors](https://docs.rubocop.org/rubocop/cops_style.html#styletrivialaccessors)
* [https://github.com/bbatsov/ruby-style-guide#attr_family](https://github.com/bbatsov/ruby-style-guide#attr_family)
