Pattern: Use of test method outside of test class

Issue: -

## Description

Checks for the use of test methods outside of a test class.

Test methods should be defined within a test class to ensure their execution.

## Examples

``` ruby
# bad
class FooTest < Minitest::Test
end
def test_method_should_be_inside_test_class
end

# good
class FooTest < Minitest::Test
  def test_method_should_be_inside_test_class
  end
end
```