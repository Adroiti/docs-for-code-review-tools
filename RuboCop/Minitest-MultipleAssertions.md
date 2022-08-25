Pattern: Too many assertion calls

Issue: -

## Description

Checks if test cases contain too many assertion calls. The maximum allowed assertion calls is configurable.

## Examples

### Max: 1

``` ruby
# bad
class FooTest < Minitest::Test
  def test_asserts_twice
    assert_equal(42, do_something)
    assert_empty(array)
  end
end

# good
class FooTest < Minitest::Test
  def test_asserts_once
    assert_equal(42, do_something)
  end

  def test_another_asserts_once
    assert_empty(array)
  end
end
```

## Configurable attributes

|      |               |                     |
|------|---------------|---------------------|
| Name | Default value | Configurable values |
| Max  | `3`           | Integer             |