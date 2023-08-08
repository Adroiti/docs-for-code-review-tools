Pattern: Malformed parentheses around stabby lambda

Issue: -

## Description

Check for parentheses around stabby lambda arguments. There are two different styles. Defaults to `require_parentheses`.

## Examples

```ruby
# require_parentheses - bad
->a,b,c { a + b + c }

# require_parentheses - good
->(a,b,c) { a + b + c}

# require_no_parentheses - bad
->(a,b,c) { a + b + c }

# require_no_parentheses - good
->a,b,c { a + b + c}
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | require_parentheses
SupportedStyles | require_parentheses, require_no_parentheses

## Further Reading

* [RuboCop - Style/StabbyLambdaParentheses](https://docs.rubocop.org/rubocop/cops_style.html#stylestabbylambdaparentheses)
* [https://github.com/bbatsov/ruby-style-guide#stabby-lambda-with-args](https://github.com/bbatsov/ruby-style-guide#stabby-lambda-with-args)
