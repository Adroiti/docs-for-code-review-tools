Pattern: Missing `type` for `@returns`

Issue: -

## Description

Requires that `@returns` tag has `type` value.

<a name="eslint-plugin-jsdoc-rules-require-returns-type-options-25"></a>
#### Options

<a name="eslint-plugin-jsdoc-rules-require-returns-type-options-25-contexts-8"></a>
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
|Tags|`returns`|
|Aliases|`return`|
|Options|`contexts`|

The following patterns are considered problems:

````js
/**
 * @returns
 */
function quux () {

}
// Message: Missing JSDoc @returns type.

/**
 * @returns Foo.
 */
function quux () {

}
// Message: Missing JSDoc @returns type.

/**
 * @returns Foo.
 */
function quux () {

}
// Options: [{"contexts":["any"]}]
// Message: Missing JSDoc @returns type.

/**
 * @function
 * @returns Foo.
 */
// Options: [{"contexts":["any"]}]
// Message: Missing JSDoc @returns type.

/**
 * @callback
 * @returns Foo.
 */
// Options: [{"contexts":["any"]}]
// Message: Missing JSDoc @returns type.

/**
 * @return Foo.
 */
function quux () {

}
// Settings: {"jsdoc":{"tagNamePreference":{"returns":"return"}}}
// Message: Missing JSDoc @return type.

/**
 * @returns
 */
function quux () {

}
// Settings: {"jsdoc":{"tagNamePreference":{"returns":false}}}
// Message: Unexpected tag `@returns`
````

The following patterns are not considered problems:

````js
/**
 * @returns {number}
 */
function quux () {

}

/**
 * @returns {number}
 */
function quux () {

}
// Options: [{"contexts":["any"]}]

/**
 * @function
 * @returns Foo.
 */

/**
 * @callback
 * @returns Foo.
 */
````


<a name="eslint-plugin-jsdoc-rules-require-returns"></a>

## Further Reading

* [eslint-plugin-jsdoc - require-returns-type](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#require-returns-type)
