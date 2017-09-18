Pattern: Malformed indentation width

Issue: -

## Description

This rule checks for indentation that doesn't use the specified number of spaces.

## Examples

```ruby
# bad, Width: 2
class A
 def test
  puts 'hello'
 end
end

# bad, Width: 2,
       IgnoredPatterns:
         - '^\s*module'
module A
class B
  def test
  puts 'hello'
  end
end
end

# good, Width: 2
class A
  def test
    puts 'hello'
  end
end

# good, Width: 2,
        IgnoredPatterns:
          - '^\s*module'
module A
class B
  def test
    puts 'hello'
  end
end
end
```

## Default configuration

Attribute | Value
--- | ---
Width | 2
IgnoredPatterns |

## Further Reading

* [RuboCop - Layout/IndentationWidth](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutindentationwidth)
* [https://github.com/bbatsov/ruby-style-guide#spaces-indentation](https://github.com/bbatsov/ruby-style-guide#spaces-indentation)
