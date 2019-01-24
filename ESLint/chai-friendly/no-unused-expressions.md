Pattern: Unused Expression

Issue: -

## Description

An unused expression which has no effect on the state of the program indicates a logic error.

This rule, in its default state, does not require any arguments. If you would like to enable one or more of the following you may pass an object with the options set as follows:

- `allowShortCircuit` set to `true` will allow you to use short circuit evaluations in your expressions (Default: `false`).
- `allowTernary` set to `true` will enable you to use ternary operators in your expressions similarly to short circuit evaluations (Default: `false`).
- `allowTaggedTemplates` set to `true` will enable you to use tagged template literals in your expressions (Default: `false`).

These options allow unused expressions only if all of the code paths either directly change the state (for example, assignment statement) or could have side effects (for example, function call).

More info in the original rule's [docs](http://eslint.org/docs/rules/no-unused-expressions#options).