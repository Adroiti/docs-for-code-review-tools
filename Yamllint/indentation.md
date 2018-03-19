Pattern: Malformed indentation

Issue: -

## Description

This rule enforces a style for indentation.

## Configuration

-   `spaces` defines the indentation width, in spaces. Set either to an integer (e.g. `2` or `4`, representing the number of spaces in an indentation level) or to `consistent` to allow any number, as long as it remains the same within the file.
-   `indent-sequences` defines whether block sequences should be indented or not (when in a mapping, this indentation is not mandatory -- some people perceive the `-` as part of the indentation). Possible values: `true`, `false`, `whatever` and `consistent`. `consistent` requires either all block sequences to be indented, or none to be. `whatever` means either indenting or not indenting individual block sequences is OK.
-   `check-multi-line-strings` defines whether to lint indentation in multi-line strings. Set to `true` to enable, `false` to disable.

## Examples

1.  With `indentation: {spaces: 1}`

    the following code snippet would **PASS**:

        history:
         - name: Unix
           date: 1969
         - name: Linux
           date: 1991
        nest:
         recurse:
          - haystack:
             needle

2.  With `indentation: {spaces: 4}`

    the following code snippet would **PASS**:

        history:
            - name: Unix
              date: 1969
            - name: Linux
              date: 1991
        nest:
            recurse:
                - haystack:
                      needle

    the following code snippet would **FAIL**:

        history:
          - name: Unix
            date: 1969
          - name: Linux
            date: 1991
        nest:
          recurse:
            - haystack:
                needle

3.  With `indentation: {spaces: consistent}`

    the following code snippet would **PASS**:

        history:
           - name: Unix
             date: 1969
           - name: Linux
             date: 1991
        nest:
           recurse:
              - haystack:
                   needle

    the following code snippet would **FAIL**:

        some:
          Russian:
              dolls

4.  With `indentation: {spaces: 2, indent-sequences: false}`

    the following code snippet would **PASS**:

        list:
        - flying
        - spaghetti
        - monster

    the following code snippet would **FAIL**:

        list:
          - flying
          - spaghetti
          - monster

5.  With `indentation: {spaces: 2, indent-sequences: whatever}`

    the following code snippet would **PASS**:

        list:
        - flying:
          - spaghetti
          - monster
        - not flying:
            - spaghetti
            - sauce

6.  With `indentation: {spaces: 2, indent-sequences: consistent}`

    the following code snippet would **PASS**:

        - flying:
          - spaghetti
          - monster
        - not flying:
          - spaghetti
          - sauce

    the following code snippet would **FAIL**:

        - flying:
            - spaghetti
            - monster
        - not flying:
          - spaghetti
          - sauce

7.  With `indentation: {spaces: 4, check-multi-line-strings: true}`

    the following code snippet would **PASS**:

        Blaise Pascal:
            Je vous écris une longue lettre parce que
            je n'ai pas le temps d'en écrire une courte.

    the following code snippet would **PASS**:

        Blaise Pascal: Je vous écris une longue lettre parce que
                       je n'ai pas le temps d'en écrire une courte.

    the following code snippet would **FAIL**:

        Blaise Pascal: Je vous écris une longue lettre parce que
          je n'ai pas le temps d'en écrire une courte.

    the following code snippet would **FAIL**:

        C code:
            void main() {
                printf("foo");
            }

    the following code snippet would **PASS**:

        C code:
            void main() {
            printf("bar");
            }

## Further Reading

* [Yamllint - indentation](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.indentation)