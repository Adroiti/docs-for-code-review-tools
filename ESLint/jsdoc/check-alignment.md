Pattern: Invalid JSDoc alignment

Issue: -

## Description

Reports invalid alignment of JSDoc block asterisks.

|||
|---|---|
|Context|everywhere|
|Tags|N/A|

The following patterns are considered problems:

````js
/**
  * @param {Number} foo
 */
function quux (foo) {
  // with spaces
}
// Message: Expected JSDoc block to be aligned.

/**
  * @param {Number} foo
 */
function quux (foo) {
	// with tabs
}
// Message: Expected JSDoc block to be aligned.

/**
  * @param {Number} foo
 */
function quux (foo) {
  // with spaces
}
// Message: Expected JSDoc block to be aligned.

/**
* @param {Number} foo
*/
function quux (foo) {
  // with spaces
}
// Message: Expected JSDoc block to be aligned.

/**
 * @param {Number} foo
  */
function quux (foo) {

}
// Message: Expected JSDoc block to be aligned.

 /**
 * @param {Number} foo
 */
function quux (foo) {

}
// Message: Expected JSDoc block to be aligned.

 /**
  * @param {Number} foo
 */
function quux (foo) {

}
// Message: Expected JSDoc block to be aligned.

/**
  * @param {Number} foo
  */
 function quux (foo) {

 }
// Message: Expected JSDoc block to be aligned.

/**
   * A jsdoc not attached to any node.
 */
// Message: Expected JSDoc block to be aligned.

class Foo {
  /**
   *  Some method
    * @param a
   */
  quux(a) {}
}
// Message: Expected JSDoc block to be aligned.
````

The following patterns are not considered problems:

````js
/**
 * Desc
 *
 * @param {Number} foo
 */
function quux (foo) {

}

/**
 * Desc
 *
 * @param {{
  foo: Bar,
  bar: Baz
 * }} foo
 *
 */
function quux (foo) {

}

/*  <- JSDoc must start with 2 stars.
  *    So this is unchecked.
 */
function quux (foo) {}

/**
  * @param {Number} foo
  * @private
 */
function quux (foo) {
  // with spaces
}
// Settings: {"jsdoc":{"ignorePrivate":true}}

/**
  * @param {Number} foo
  * @access private
 */
function quux (foo) {
  // with spaces
}
// Settings: {"jsdoc":{"ignorePrivate":true}}
````


<a name="eslint-plugin-jsdoc-rules-check-examples"></a>

## Further Reading

* [eslint-plugin-jsdoc - check-alignment](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#check-alignment)
