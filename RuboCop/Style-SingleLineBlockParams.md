Pattern: Style/SingleLineBlockParams

Issue: -

## Description

This cop checks whether the block parameters of a single-line
method accepting a block match the names specified via configuration.

For instance one can configure `reduce`(`inject`) to use |a, e| as
parameters.

## Default configuration

Attribute | Value
--- | ---
Methods | {"reduce"=>["acc", "elem"]}, {"inject"=>["acc", "elem"]}

## Further Reading

* [RuboCop - Style/SingleLineBlockParams](https://rubocop.readthedocs.io/en/latest/cops_style/#stylesinglelineblockparams)
