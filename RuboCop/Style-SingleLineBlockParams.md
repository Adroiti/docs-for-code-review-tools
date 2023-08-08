Pattern: Mismatched single line block params

Issue: -

## Description

This rule checks whether the block parameters of a single-line method accepting a block match the names specified via configuration.

For instance one can configure `reduce`(`inject`) to use |a, e| as parameters.

## Default configuration

Attribute | Value
--- | ---
Methods | {"reduce"=>["acc", "elem"]}, {"inject"=>["acc", "elem"]}

## Further Reading

* [RuboCop - Style/SingleLineBlockParams](https://docs.rubocop.org/rubocop/cops_style.html#stylesinglelineblockparams)
