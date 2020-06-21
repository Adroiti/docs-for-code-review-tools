Pattern: Class ends with blank line

Issue: -

## Description

Checks whether the class ends with a blank line. By default, it enforces that there must be a blank line before the closing class brace, except
if the class is empty and is written in a single line. A blank line is defined as any line that does not contain any visible characters.

Examples of violations:

If ignoreSingleLineClasses is `true` and blankLineRequired is `true`

``` groovy
        class Foo {
            int a

            void hi() {
            }
        }
```

If ignoreSingleLineClasses is `false` and blankLineRequired is `true`

``` groovy
        class Foo extends Bar<String> { }
```

If ignoreSingleLineClasses is `true` and blankLineRequired is `false`

``` groovy
        class Foo {
            int a

            void hi() {
            }

        }
```

If ignoreSingleLineClasses is `false` and blankLineRequired is `false`

``` groovy
        class Foo {
            int a

            void hi() {
            }

        }
```

## Further Reading

* [CodeNarc - ClassEndsWithBlankLine](https://codenarc.github.io/CodeNarc/codenarc-rules-formatting.html#classendswithblankline-rule)