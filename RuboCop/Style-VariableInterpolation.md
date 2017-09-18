Pattern: Direct variable interpolation

Issue: -

## Description

This rule checks for variable interpolation (like `#@ivar`).

## Examples

```ruby
class Person
  attr_reader :first_name, :last_name

  def initialize(first_name, last_name)
    @first_name = first_name
    @last_name = last_name
  end

  # bad - valid, but awkward
  def to_s
    "#@first_name #@last_name"
  end

  # good
  def to_s
    "#{@first_name} #{@last_name}"
  end
end

$global = 0
# bad
puts "$global = #$global"

# good
puts "$global = #{$global}"
```

## Further Reading

* [RuboCop - Style/VariableInterpolation](https://rubocop.readthedocs.io/en/latest/cops_style/#stylevariableinterpolation)
* [https://github.com/bbatsov/ruby-style-guide#curlies-interpolate](https://github.com/bbatsov/ruby-style-guide#curlies-interpolate)
