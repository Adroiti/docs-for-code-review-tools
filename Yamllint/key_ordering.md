Pattern: Wrong order of mapping keys

Issue: -

## Description

This rule enforces alphabetical ordering of keys in mappings. The sorting order uses the Unicode code point number. As a result, the ordering is case-sensitive and not accent-friendly (see examples below).

## Examples

1.  With `key-ordering: {}`

    the following code snippet would **PASS**:

        - key 1: v
          key 2: val
          key 3: value
        - {a: 1, b: 2, c: 3}
        - T-shirt: 1
          T-shirts: 2
          t-shirt: 3
          t-shirts: 4
        - hair: true
          hais: true
          haïr: true
          haïssable: true

    the following code snippet would **FAIL**:

        - key 2: v
          key 1: val

    the following code snippet would **FAIL**:

        - {b: 1, a: 2}

    the following code snippet would **FAIL**:

        - T-shirt: 1
          t-shirt: 2
          T-shirts: 3
          t-shirts: 4

    the following code snippet would **FAIL**:

        - haïr: true
          hais: true

## Further Reading

* [Yamllint - key_ordering](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.key_ordering)