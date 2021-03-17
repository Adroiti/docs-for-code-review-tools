Pattern: Undocumented yield

Issue: -

## Description

Requires that yields are documented.

Will also report if multiple `@yields` tags are present.


The following patterns are considered problems:

```js
/**
 *
 */
function * quux (foo) {

  yield foo;
}
// Message: Missing JSDoc @yields declaration.

/**
 * @yields
 */
function * quux (foo) {

  const retVal = yield foo;
}
// "jsdoc/require-yields": ["error"|"warn", {"next":true}]
// Message: Missing JSDoc @next declaration.

/**
 * @yields
 */
function * quux (foo) {

  const retVal = yield;
}
// "jsdoc/require-yields": ["error"|"warn", {"next":true}]
// Message: Missing JSDoc @next declaration.

/**
 * @yields {void}
 */
function * quux () {
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireNext":true}]
// Message: Missing JSDoc @next declaration.

/**
 * @yields {void}
 */
function * quux () {
  yield;
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireNext":true}]
// Message: Missing JSDoc @next declaration.

/**
 *
 */
function * quux (foo) {

  const a = yield foo;
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux (foo) {
  yield foo;
}
// Settings: {"jsdoc":{"tagNamePreference":{"yields":"yield"}}}
// Message: Missing JSDoc @yield declaration.

/**
 * @yields
 */
function * quux (foo) {
  const val = yield foo;
}
// Settings: {"jsdoc":{"tagNamePreference":{"next":"yield-returns"}}}
// "jsdoc/require-yields": ["error"|"warn", {"next":true}]
// Message: Missing JSDoc @yield-returns declaration.

/**
 * @yields
 * @next
 */
function * quux () {
  const ret = yield 5;
}
// Settings: {"jsdoc":{"tagNamePreference":{"next":false}}}
// "jsdoc/require-yields": ["error"|"warn", {"next":true}]
// Message: Unexpected tag `@next`

/**
 *
 */
function * quux() {
  yield 5;
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux() {
  yield;
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
const quux = async function * () {
  yield;
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
async function * quux () {
  yield;
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  yield;
}
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"forceRequireYields":true}]
// Message: Missing JSDoc @yields declaration.

/**
 * @function
 * @generator
 */
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"forceRequireYields":true}]
// Message: Missing JSDoc @yields declaration.

/**
 * @callback
 * @generator
 */
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"forceRequireYields":true}]
// Message: Missing JSDoc @yields declaration.

/**
 * @yields {undefined}
 * @yields {void}
 */
function * quux (foo) {

  return foo;
}
// Message: Found more than one @yields declaration.

/**
 * @yields
 */
function * quux () {

}
// Settings: {"jsdoc":{"tagNamePreference":{"yields":false}}}
// Message: Unexpected tag `@yields`

/**
 * @param foo
 */
function * quux (foo) {
  yield 'bar';
}
// "jsdoc/require-yields": ["error"|"warn", {"exemptedBy":["notPresent"]}]
// Message: Missing JSDoc @yields declaration.

/**
 * @param {array} a
 */
async function * foo(a) {
  return;
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]
// Message: Missing JSDoc @yields declaration.

/**
 * @param {array} a
 */
async function * foo(a) {
  yield Promise.all(a);
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]
// Message: Missing JSDoc @yields declaration.

class quux {
  /**
   *
   */
  * quux () {
    yield;
  }
}
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"forceRequireYields":true}]
// Message: Missing JSDoc @yields declaration.

/**
 * @param {array} a
 */
async function * foo(a) {
  yield Promise.all(a);
}
// Message: Missing JSDoc @yields declaration.

/**
 * @generator
 */
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"withGeneratorTag":true}]
// Message: Missing JSDoc @yields declaration.

/**
 * @generator
 * @yields
 */
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"nextWithGeneratorTag":true}]
// Message: Missing JSDoc @next declaration.

/**
 *
 */
function * quux () {
  if (true) {
    yield;
  }
  yield true;
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  try {
    yield true;
  } catch (err) {
  }
  yield;
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  try {
  } finally {
    yield true;
  }
  yield;
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  try {
    yield;
  } catch (err) {
  }
  yield true;
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  try {
    something();
  } catch (err) {
    yield true;
  }
  yield;
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  switch (true) {
  case 'abc':
    yield true;
  }
  yield;
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  switch (true) {
  case 'abc':
    yield;
  }
  yield true;
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  for (const i of abc) {
    yield true;
  }
  yield;
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  for (const a in b) {
    yield true;
  }
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  for (let i=0; i<n; i+=1) {
    yield true;
  }
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  while(true) {
    yield true
  }
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  do {
    yield true
  }
  while(true)
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  if (true) {
    yield;
  }
  yield true;
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  if (true) {
    yield true;
  }
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  var a = {};
  with (a) {
    yield true;
  }
}
// Message: Missing JSDoc @yields declaration.

/**
 *
 */
function * quux () {
  if (true) {
    yield;
  } else {
    yield true;
  }
  yield;
}
// Message: Missing JSDoc @yields declaration.
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
 * @yields Foo.
 */
function * quux () {

  yield foo;
}
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"]}]

/**
 *
 */
function * quux () {
}

/**
 *
 */
function * quux () {
  yield;
}

/**
 *
 */
function quux (bar) {
  bar.doSomething(function * (baz) {
    yield baz.corge();
  })
}

/**
 * @yields {Array}
 */
function * quux (bar) {
  yield bar.doSomething(function * (baz) {
    yield baz.corge();
  })
}

/**
 * @inheritdoc
 */
function * quux (foo) {
}

/**
 * @override
 */
function * quux (foo) {
}

/**
 * @constructor
 */
function * quux (foo) {
}

/**
 * @implements
 */
function * quux (foo) {
  yield;
}

/**
 * @override
 */
function * quux (foo) {

  yield foo;
}

/**
 * @class
 */
function * quux (foo) {
  yield foo;
}

/**
 * @constructor
 */
function * quux (foo) {
}

/**
 * @yields {object}
 */
function * quux () {

  yield {a: foo};
}

/**
 * @yields {void}
 */
function * quux () {
}

/**
 * @yields {undefined}
 */
function * quux () {
}

/**
 *
 */
function * quux () {
}

/**
 * @yields {void}
 */
function quux () {
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]

/**
 * @yields {void}
 * @next {void}
 */
function * quux () {
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireNext":true}]

/**
 * @yields {void}
 */
function * quux () {
  yield undefined;
}

/**
 * @yields {void}
 */
function * quux () {
  yield undefined;
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]

/**
 * @yields {void}
 */
function * quux () {
  yield;
}

/**
 * @yields {void}
 */
function * quux () {
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]

/**
 * @yields {void}
 */
function * quux () {
  yield;
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]

/** @type {SpecialIterator} */
function * quux () {
  yield 5;
}

/**
 * @yields {Something}
 */
async function * quux () {
}
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]

/**
 *
 */
async function * quux () {}

/**
 *
 */
const quux = async function * () {}

/**
 * @type {MyCallback}
 */
function * quux () {
  yield;
}
// "jsdoc/require-yields": ["error"|"warn", {"exemptedBy":["type"]}]

/**
 * @param {array} a
 */
async function * foo (a) {
  yield;
}

/**
 *
 */
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"]}]

/**
 * @function
 */
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"]}]

/**
 * @function
 */
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]

/**
 * @callback
 */
// "jsdoc/require-yields": ["error"|"warn", {"forceRequireYields":true}]

/**
 * @generator
 */
// "jsdoc/require-yields": ["error"|"warn", {"withGeneratorTag":true}]

/**
 * @generator
 */
// "jsdoc/require-yields": ["error"|"warn", {"nextWithGeneratorTag":true}]

/**
 * @generator
 * @yields
 */
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"withGeneratorTag":true}]

/**
 * @generator
 * @yields
 * @next
 */
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"nextWithGeneratorTag":true}]

/**
 * @generator
 */
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"withGeneratorTag":false}]

/**
 * @generator
 * @yields
 */
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"nextWithGeneratorTag":false}]

/**
 * @yields
 */
function * quux (foo) {

  const a = yield foo;
}

/**
 * @yields
 * @next
 */
function * quux (foo) {
  let a = yield;
}
// "jsdoc/require-yields": ["error"|"warn", {"next":true}]

/**
 * @yields
 * @next
 */
function * quux (foo) {
  const a = yield foo;
}
// "jsdoc/require-yields": ["error"|"warn", {"next":true}]

/**
 *
 */
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"nextWithGeneratorTag":true}]

/**
 *
 */
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"next":true}]

/**
 *
 */
function quux () {}
// "jsdoc/require-yields": ["error"|"warn", {"contexts":["any"],"next":true}]

/**
 * @yields {void}
 */
function * quux () {
  yield;
}
// "jsdoc/require-yields": ["error"|"warn", {"next":true}]

/**
 *
 */
function * quux (foo) {
  const a = function * bar () {
    yield foo;
  }
}
```

## Further Reading

* [eslint-plugin-jsdoc - require-yields](https://github.com/gajus/eslint-plugin-jsdoc#require-yields)
