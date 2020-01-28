Pattern: Invalid Closure syntax

Issue: -

## Description

Reports against Google Closure Compiler syntax.

|||
|---|---|
|Context|everywhere|
|Tags|N/A|

The following patterns are considered problems:

````js
/**
 * @param {string=} foo
 */
function quux (foo) {

}
// Message: Syntax should not be Google Closure Compiler style.
````

The following patterns are not considered problems:

````js
/**
 * @param {string} [foo]
 */
function quux (foo) {

}

/**
 *
 */
function quux (foo) {

}
````


<a name="eslint-plugin-jsdoc-rules-check-tag-names"></a>

## Further Reading

* [eslint-plugin-jsdoc - check-syntax](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#check-syntax)
