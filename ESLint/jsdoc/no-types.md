Pattern: Use of restricted `@param`/`@returns` type

Issue: -

## Description

This rule reports types being used on `@param` or `@returns`.

The rule is intended to prevent the indication of types on tags where
the type information would be redundant with TypeScript.

<a name="eslint-plugin-jsdoc-rules-no-types-options-12"></a>
#### Options

<a name="eslint-plugin-jsdoc-rules-no-types-options-12-contexts-2"></a>
##### <code>contexts</code>

Set this to an array of strings representing the AST context
where you wish the rule to be applied.
Overrides the default contexts (see below). Set to `"any"` if you want
the rule to apply to any jsdoc block throughout your files (as is necessary
for finding function blocks not attached to a function declaration or
expression, i.e., `@callback` or `@function` (or its aliases `@func` or
`@method`) (including those associated with an `@interface`).

|||
|---|---|
|Context|`ArrowFunctionExpression`, `FunctionDeclaration`, `FunctionExpression`; others when `contexts` option enabled|
|Tags|`param`, `returns`|
|Aliases|`arg`, `argument`, `return`|
|Options|`contexts`|

The following patterns are considered problems:

````js
/**
 * @param {number} foo
 */
function quux (foo) {

}
// Message: Types are not permitted on @param.

/**
 * @param {number} foo
 */
function quux (foo) {

}
// Options: [{"contexts":["any"]}]
// Message: Types are not permitted on @param.

/**
 * @function
 * @param {number} foo
 */
// Options: [{"contexts":["any"]}]
// Message: Types are not permitted on @param.

/**
 * @callback
 * @param {number} foo
 */
// Options: [{"contexts":["any"]}]
// Message: Types are not permitted on @param.

/**
 * @returns {number}
 */
function quux () {

}
// Message: Types are not permitted on @returns.
````

The following patterns are not considered problems:

````js
/**
 * @param foo
 */
function quux (foo) {

}

/**
 * @param foo
 */
// Options: [{"contexts":["any"]}]

/**
 * @function
 * @param {number} foo
 */

/**
 * @callback
 * @param {number} foo
 */
````


<a name="eslint-plugin-jsdoc-rules-no-undefined-types"></a>

## Further Reading

* [eslint-plugin-jsdoc - no-types](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#no-types)
