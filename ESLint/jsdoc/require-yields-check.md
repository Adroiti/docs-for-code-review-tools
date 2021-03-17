Pattern: Malformed `@yields`

Issue: -

## Description

Ensures that if a `@yields` is present that a `yield` (or `yield` with a
value) is present in the function body (or that if a `@next` is present that
there is a `yield` with a return value present).

Please also note that JavaScript does allow generators not to have `yield`
(e.g., with just a return or even no explicit return), but if you want to
enforce that all generators (except wholly empty ones) have a `yield` in the
function body, you can use the ESLint
[`require-yield`](https://eslint.org/docs/rules/require-yield) rule. In
conjunction with this, you can also use the `checkGeneratorsOnly` option
as an optimization so that this rule won't need to do its own checking within
function bodies.

Will also report if multiple `@yields` tags are present.


The following patterns are considered problems:

```js
/**
 * @yields
 */
function * quux (foo) {

}
// Message: JSDoc @yields declaration present but yield expression not available in function.

/**
 * @yields
 */
function quux (foo) {

}
// "jsdoc/require-yields-check": ["error"|"warn", {"checkGeneratorsOnly":true}]
// Message: JSDoc @yields declaration present but yield expression not available in function.

/**
 * @next
 */
function quux (foo) {

}
// "jsdoc/require-yields-check": ["error"|"warn", {"checkGeneratorsOnly":true,"next":true}]
// Message: JSDoc @next declaration present but yield expression with return value not available in function.

/**
 * @next {SomeType}
 */
function * quux (foo) {

}
// "jsdoc/require-yields-check": ["error"|"warn", {"next":true}]
// Message: JSDoc @next declaration present but yield expression with return value not available in function.

/**
 * @next {SomeType}
 */
function * quux (foo) {
  yield;
}
// "jsdoc/require-yields-check": ["error"|"warn", {"next":true}]
// Message: JSDoc @next declaration present but yield expression with return value not available in function.

/**
 * @next {SomeType}
 */
function * quux (foo) {
  yield 5;
}
// "jsdoc/require-yields-check": ["error"|"warn", {"next":true}]
// Message: JSDoc @next declaration present but yield expression with return value not available in function.

/**
 * @yield
 */
function * quux (foo) {

}
// Settings: {"jsdoc":{"tagNamePreference":{"yields":"yield"}}}
// Message: JSDoc @yield declaration present but yield expression not available in function.

/**
 * @yield-returns {Something}
 */
function * quux (foo) {
  yield;
}
// Settings: {"jsdoc":{"tagNamePreference":{"next":"yield-returns"}}}
// "jsdoc/require-yields-check": ["error"|"warn", {"next":true}]
// Message: JSDoc @yield-returns declaration present but yield expression with return value not available in function.

/**
 * @yields {undefined} Foo.
 * @yields {String} Foo.
 */
function * quux () {

  yield foo;
}
// Message: Found more than one @yields declaration.

class Foo {
  /**
   * @yields {string}
   */
  * bar () {
  }
}
// Message: JSDoc @yields declaration present but yield expression not available in function.

/**
 * @yields
 */
function * quux () {

}
// Settings: {"jsdoc":{"tagNamePreference":{"yields":false}}}
// Message: Unexpected tag `@yields`

/**
 * @next
 */
function * quux () {

}
// Settings: {"jsdoc":{"tagNamePreference":{"next":false}}}
// "jsdoc/require-yields-check": ["error"|"warn", {"next":true}]
// Message: Unexpected tag `@next`

/**
 * @yields {string}
 */
function * f () {
  function * g() {
    yield 'foo'
  }
}
// Message: JSDoc @yields declaration present but yield expression not available in function.

/**
 * @yields {Promise<void>}
 */
async function * quux() {}
// Message: JSDoc @yields declaration present but yield expression not available in function.

/**
 * @yields {Promise<void>}
 */
const quux = async function * () {}
// Message: JSDoc @yields declaration present but yield expression not available in function.
````

The following patterns are not considered problems:

````js
/**
 * @yields Foo.
 */
function * quux () {

  yield foo;
}

/**
 * @yields {string} Foo.
 */
function * quux () {

  yield foo;
}

/**
 * @yields {string} Foo.
 */
function * quux () {

  yield foo;
}

/**
 *
 */
function * quux () {
}

/**
 * @yields {undefined} Foo.
 */
function * quux () {}

/**
 * @yields { void } Foo.
 */
function quux () {}

/**
 * @yields Foo.
 * @abstract
 */
function * quux () {
  throw new Error('must be implemented by subclass!');
}

/**
 * @yields Foo.
 * @virtual
 */
function * quux () {
  throw new Error('must be implemented by subclass!');
}

/**
 * @yields Foo.
 * @constructor
 */
function * quux () {
}

/**
 * @interface
 */
class Foo {
  /**
   * @yields {string}
   */
  * bar () {
  }
}

/**
 * @record
 */
class Foo {
  /**
   * @yields {string}
   */
  * bar () {
  }
}
// Settings: {"jsdoc":{"mode":"closure"}}

/**
 * @yields {undefined} Foo.
 */
function * quux () {
}

/**
 * @yields {void} Foo.
 */
function * quux () {
}

/**
 * @yields {void} Foo.
 */
function * quux () {
  yield undefined;
}

/**
 * @yields {void} Foo.
 */
function * quux () {
  yield;
}

/**
 *
 */
function * quux () {
  yield undefined;
}

/**
 *
 */
function * quux () {
  yield;
}

/**
 * @yields {true}
 */
function * quux () {
  try {
    yield true;
  } catch (err) {
  }
  yield;
}

/**
 * @yields {true}
 */
function * quux () {
  try {
  } finally {
    yield true;
  }
  yield;
}

/**
 * @yields {true}
 */
function * quux () {
  try {
    yield;
  } catch (err) {
  }
  yield true;
}

/**
 * @yields {true}
 */
function * quux () {
  try {
    something();
  } catch (err) {
    yield true;
  }
  yield;
}

/**
 * @yields {true}
 */
function * quux () {
  switch (true) {
  case 'abc':
    yield true;
  }
  yield;
}

/**
 * @yields {true}
 */
function * quux () {
  switch (true) {
  case 'abc':
    yield;
  }
  yield true;
}

/**
 * @yields {true}
 */
function * quux () {
  for (const i of abc) {
    yield true;
  }
  yield;
}

/**
 * @yields {true}
 */
function * quux () {
  for (const a in b) {
    yield true;
  }
}

/**
 * @yields {true}
 */
function * quux () {
  for (let i=0; i<n; i+=1) {
    yield true;
  }
}

/**
 * @yields {true}
 */
function * quux () {
  while(true) {
    yield true
  }
}

/**
 * @yields {true}
 */
function * quux () {
  do {
    yield true
  }
  while(true)
}

/**
 * @yields {true}
 */
function * quux () {
  if (true) {
    yield;
  }
  yield true;
}

/**
 * @yields {true}
 */
function * quux () {
  if (true) {
    yield true;
  }
}

/**
 * @yields {true}
 */
function * quux () {
  var a = {};
  with (a) {
    yield true;
  }
}

/**
 * @yields {true}
 */
function * quux () {
  if (true) {
    yield;
  } else {
    yield true;
  }
  yield;
}

/**
 * @next {void}
 */
function * quux (foo) {

}
// "jsdoc/require-yields-check": ["error"|"warn", {"next":true}]

/**
 * @next {SomeType}
 */
function * quux (foo) {
  const a = yield;
}
// "jsdoc/require-yields-check": ["error"|"warn", {"next":true}]

/**
 * @next {SomeType}
 */
function * quux (foo) {
  const a = yield 5;
}
// "jsdoc/require-yields-check": ["error"|"warn", {"next":true}]
```

## Further Reading

* [eslint-plugin-jsdoc - require-yields-check](https://github.com/gajus/eslint-plugin-jsdoc#require-yields-check)
