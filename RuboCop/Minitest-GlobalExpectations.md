Pattern: Deprecated global expectation

Issue: -

## Description

Checks for deprecated global expectations and autocorrects them to use expect format.

## Examples

### EnforcedStyle: any (default)

``` ruby
# bad
musts.must_equal expected_musts
wonts.wont_match expected_wonts
musts.must_raise TypeError

# good
_(musts).must_equal expected_musts
_(wonts).wont_match expected_wonts
_ { musts }.must_raise TypeError

expect(musts).must_equal expected_musts
expect(wonts).wont_match expected_wonts
expect { musts }.must_raise TypeError

value(musts).must_equal expected_musts
value(wonts).wont_match expected_wonts
value { musts }.must_raise TypeError
```

### EnforcedStyle: \_

``` ruby
# bad
musts.must_equal expected_musts
wonts.wont_match expected_wonts
musts.must_raise TypeError

expect(musts).must_equal expected_musts
expect(wonts).wont_match expected_wonts
expect { musts }.must_raise TypeError

value(musts).must_equal expected_musts
value(wonts).wont_match expected_wonts
value { musts }.must_raise TypeError

# good
_(musts).must_equal expected_musts
_(wonts).wont_match expected_wonts
_ { musts }.must_raise TypeError
```

### EnforcedStyle: expect

``` ruby
# bad
musts.must_equal expected_musts
wonts.wont_match expected_wonts
musts.must_raise TypeError

_(musts).must_equal expected_musts
_(wonts).wont_match expected_wonts
_ { musts }.must_raise TypeError

value(musts).must_equal expected_musts
value(wonts).wont_match expected_wonts
value { musts }.must_raise TypeError

# good
expect(musts).must_equal expected_musts
expect(wonts).wont_match expected_wonts
expect { musts }.must_raise TypeError
```

### EnforcedStyle: value

``` ruby
# bad
musts.must_equal expected_musts
wonts.wont_match expected_wonts
musts.must_raise TypeError

_(musts).must_equal expected_musts
_(wonts).wont_match expected_wonts
_ { musts }.must_raise TypeError

expect(musts).must_equal expected_musts
expect(wonts).wont_match expected_wonts
expect { musts }.must_raise TypeError

# good
value(musts).must_equal expected_musts
value(wonts).wont_match expected_wonts
value { musts }.must_raise TypeError
```

## Configurable attributes

|               |                                                                        |                               |
|---------------|------------------------------------------------------------------------|-------------------------------|
| Name          | Default value                                                          | Configurable values           |
| EnforcedStyle | `any`                                                                  | `_`, `any`, `expect`, `value` |
| Include       | `+**/test/**/*+`, `+**/*_test.rb+`, `+**/spec/**/*+`, `+**/*_spec.rb+` | Array                         |

## Further Reading

- <https://minitest.rubystyle.guide#global-expectations>