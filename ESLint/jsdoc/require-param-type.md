Pattern: Missing `type` for `@param`

Issue: -

## Description

Requires that each `@param` tag has a `type` value.

<a name="eslint-plugin-jsdoc-rules-require-param-type-options-22"></a>
#### Options

<a name="eslint-plugin-jsdoc-rules-require-param-type-options-22-contexts-6"></a>
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
|Tags|`param`|
|Aliases|`arg`, `argument`|
|Options|`contexts`|

The following patterns are considered problems:

````js
/**
 * @param foo
 */
function quux (foo) {

}
// Message: Missing JSDoc @param "foo" type.

/**
 * @param foo
 */
function quux (foo) {

}
// Options: [{"contexts":["any"]}]
// Message: Missing JSDoc @param "foo" type.

/**
 * @function
 * @param foo
 */
// Options: [{"contexts":["any"]}]
// Message: Missing JSDoc @param "foo" type.

/**
 * @callback
 * @param foo
 */
// Options: [{"contexts":["any"]}]
// Message: Missing JSDoc @param "foo" type.

/**
 * @arg foo
 */
function quux (foo) {

}
// Settings: {"jsdoc":{"tagNamePreference":{"param":"arg"}}}
// Message: Missing JSDoc @arg "foo" type.

/**
 * @param foo
 */
function quux (foo) {

}
// Settings: {"jsdoc":{"tagNamePreference":{"param":false}}}
// Message: Unexpected tag `@param`
````

The following patterns are not considered problems:

````js
/**
 *
 */
function quux (foo) {

}

/**
 * @param {number} foo
 */
function quux (foo) {

}

/**
 * @param {number} foo
 */
function quux (foo) {

}
// Options: [{"contexts":["any"]}]

/**
 * @function
 * @param foo
 */

/**
 * @callback
 * @param foo
 */
````


<a name="eslint-plugin-jsdoc-rules-require-param"></a>

## Further Reading

* [eslint-plugin-jsdoc - require-param-type](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#require-param-type)
