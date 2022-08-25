Pattern: Missing use of `test_` prefix

Issue: -

## Description

Enforces that test method names start with `test_` prefix. It aims to
prevent tests that aren’t executed by forgetting to start test method
name with `test_`.

## Examples

``` ruby
# bad
class FooTest < Minitest::Test
  def does_something
    assert_equal 42, do_something
  end
end

# good
class FooTest < Minitest::Test
  def test_does_something
    assert_equal 42, do_something
  end
end

# good
class FooTest < Minitest::Test
  def helper_method(argument)
  end
end
```