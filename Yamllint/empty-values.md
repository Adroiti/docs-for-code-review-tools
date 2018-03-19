Pattern: Node with empty content

Issue: -

## Description

This rule forbids nodes with empty content, that implicitly result in `null` values.

## Configuration

-   Use `forbid-in-block-mappings` to prevent empty values in block mappings.
-   Use `forbid-in-flow-mappings` to prevent empty values in flow mappings.

## Examples

1.  With `empty-values: {forbid-in-block-mappings: true}`

    the following code snippets would **PASS**:

        some-mapping:
          sub-element: correctly indented

        explicitly-null: null

    the following code snippets would **FAIL**:

        some-mapping:
        sub-element: incorrectly indented

        implicitly-null:

2.  With `empty-values: {forbid-in-flow-mappings: true}`

    the following code snippet would **PASS**:

        {prop: null}
        {a: 1, b: 2, c: 3}

    the following code snippets would **FAIL**:

        {prop: }

        {a: 1, b:, c: 3}

## Further Reading

* [Yamllint - empty_values](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.empty_values)