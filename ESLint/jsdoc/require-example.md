Pattern: Missing function JSDoc example

Issue: -

## Description

Requires that all functions have examples.

* All functions must have one or more `@example` tags.
* Every example tag must have a non-empty description that explains the method's usage.

<a name="eslint-plugin-jsdoc-rules-require-example-options-16"></a>
#### Options

This rule has an object option.

<a name="eslint-plugin-jsdoc-rules-require-example-options-16-exemptedby"></a>
##### <code>exemptedBy</code>

Array of tags (e.g., `['type']`) whose presence on the document
block avoids the need for an `@example`. Defaults to an empty array.

<a name="eslint-plugin-jsdoc-rules-require-example-options-16-avoidexampleonconstructors"></a>
##### <code>avoidExampleOnConstructors</code>

Set to `true` to avoid the need for an example on a constructor (whether
indicated as such by a jsdoc tag or by being within an ES6 `class`).
Defaults to `false`.

<a name="eslint-plugin-jsdoc-rules-require-example-options-16-contexts-3"></a>
##### <code>contexts</code>

Set this to an array of strings representing the AST context
where you wish the rule to be applied (e.g., `ClassDeclaration` for ES6 classes).
Overrides the default contexts (see below). Set to `"any"` if you want
the rule to apply to any jsdoc block throughout your files.

<a name="eslint-plugin-jsdoc-rules-require-example-fixer"></a>
#### Fixer

The fixer for `require-example` will add an empty `@example`, but it will still
report a missing example description after this is added.

|||
|---|---|
|Context|`ArrowFunctionExpression`, `FunctionDeclaration`, `FunctionExpression`; others when `contexts` option enabled|
|Tags|`example`|
|Options|`exemptedBy`, `avoidExampleOnConstructors`, `contexts`|
|Settings|`overrideReplacesDocs`, `augmentsExtendsReplacesDocs`, `implementsReplacesDocs`|

The following patterns are considered problems:

````js
/**
 *
 */
function quux () {

}
// Message: Missing JSDoc @example declaration.

/**
 * @example
 */
function quux () {

}
// Message: Missing JSDoc @example description.

/**
 * @constructor
 */
function f () {

}
// Settings: {"jsdoc":{"avoidExampleOnConstructors":true}}
// Message: `settings.jsdoc.avoidExampleOnConstructors` has been removed, use options in the rule `require-example` instead.

/**
 * @constructor
 */
function quux () {

}
// Message: Missing JSDoc @example declaration.

/**
 * @constructor
 * @example
 */
function quux () {

}
// Message: Missing JSDoc @example description.

/**
 *
 */
class quux {

}
// Options: [{"contexts":["ClassDeclaration"]}]
// Message: Missing JSDoc @example declaration.

/**
 *
 */
// Options: [{"contexts":["any"]}]
// Message: Missing JSDoc @example declaration.

/**
 *
 */
function quux () {
}
// Options: [{"exemptedBy":["notPresent"]}]
// Message: Missing JSDoc @example declaration.
````

The following patterns are not considered problems:

````js
/**
 *
 */

/**
 * @example
 * // arbitrary example content
 */
function quux () {

}

/**
 * @example
 * quux(); // does something useful
 */
function quux () {

}

/**
 * @example <caption>Valid usage</caption>
 * quux(); // does something useful
 *
 * @example <caption>Invalid usage</caption>
 * quux('random unwanted arg'); // results in an error
 */
function quux () {

}

/**
 * @constructor
 */
function quux () {

}
// Options: [{"avoidExampleOnConstructors":true}]

/**
 * @constructor
 * @example
 */
function quux () {

}
// Options: [{"avoidExampleOnConstructors":true}]

class Foo {
  /**
   *
   */
  constructor () {

  }
}
// Options: [{"avoidExampleOnConstructors":true}]

/**
 * @inheritdoc
 */
function quux () {

}

/**
 * @type {MyCallback}
 */
function quux () {

}
// Options: [{"exemptedBy":["type"]}]

/**
 * @example Some example code
 */
class quux {

}
// Options: [{"contexts":["ClassDeclaration"]}]

/**
 *
 */
function quux () {

}
// Options: [{"contexts":["ClassDeclaration"]}]
````


<a name="eslint-plugin-jsdoc-rules-require-file-overview"></a>

## Further Reading

* [eslint-plugin-jsdoc - require-example](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#require-example)
