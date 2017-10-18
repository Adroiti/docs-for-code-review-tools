Pattern: Malformed whitespace in `{}`

Issue: -

## Description

This rule checks to see that there is the proper spacing inside curly braces. 

The spacing amount is specified by `spaces` parameter. The spacing amount for empty objects is specified by `empty_object_spaces`.

## Examples

``` coffeescript
# Spaces is 0
{a: b}     # Good
{a: b }    # Bad
{ a: b}    # Bad
{ a: b }   # Bad


# Spaces is 1
{a: b}     # Bad
{a: b }    # Bad
{ a: b}    # Bad
{ a: b }   # Good
{ a: b  }  # Bad
{  a: b }  # Bad
{  a: b  } # Bad


# Empty Object Spaces is 0
{}         # Good
{ }        # Bad


# Empty Object Spaces is 1
{}         # Bad
{ }        # Good
```

## Further Reading

* [CoffeeLint - braces_spacing](http://www.coffeelint.org/#options)