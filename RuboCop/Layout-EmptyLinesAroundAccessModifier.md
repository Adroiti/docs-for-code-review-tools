Pattern: Missing blank lines around access modifier

Issue: -

## Description

Access modifiers should be surrounded by blank lines.

## Examples

```ruby
# bad
class Foo
  def bar; end
  private
  def baz; end
end

# good
class Foo
  def bar; end

  private

  def baz; end
end
```

## Further Reading

* [RuboCop - Layout/EmptyLinesAroundAccessModifier](https://docs.rubocop.org/rubocop/cops_layout.html#layoutemptylinesaroundaccessmodifier)
* [https://github.com/bbatsov/ruby-style-guide#empty-lines-around-access-modifier](https://github.com/bbatsov/ruby-style-guide#empty-lines-around-access-modifier)
