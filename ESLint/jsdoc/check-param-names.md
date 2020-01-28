Pattern: Invalid JSDoc param name

Issue: -

## Description

Ensures that parameter names in JSDoc match those in the function declaration.

<a name="eslint-plugin-jsdoc-rules-check-param-names-options-3"></a>
#### Options

<a name="eslint-plugin-jsdoc-rules-check-param-names-options-3-allowextratrailingparamdocs"></a>
##### <code>allowExtraTrailingParamDocs</code>

If set to `true`, this option will allow extra `@param` definitions (e.g.,
representing future expected or virtual params) to be present without needing
their presence within the function signature. Other inconsistencies between
`@param`'s and present function parameters will still be reported.

|||
|---|---|
|Context|`ArrowFunctionExpression`, `FunctionDeclaration`, `FunctionExpression`|
|Options|`allowExtraTrailingParamDocs`|
|Tags|`param`|

The following patterns are considered problems:

````js
/**
 * @param Foo
 */
function quux (foo = 'FOO') {

}
// Message: Expected @param names to be "foo". Got "Foo".

/**
 * @arg Foo
 */
function quux (foo = 'FOO') {

}
// Settings: {"jsdoc":{"tagNamePreference":{"param":"arg"}}}
// Message: Expected @arg names to be "foo". Got "Foo".

/**
 * @param Foo
 */
function quux (foo) {

}
// Message: Expected @param names to be "foo". Got "Foo".

/**
 * @param Foo.Bar
 */
function quux (foo) {

}
// Message: @param path declaration ("Foo.Bar") appears before any real parameter.

/**
 * @param foo
 * @param Foo.Bar
 */
function quux (foo) {

}
// Message: @param path declaration ("Foo.Bar") root node name ("Foo") does not match previous real parameter name ("foo").

/**
 * Assign the project to a list of employees.
 * @param {string} employees[].name - The name of an employee.
 * @param {string} employees[].department - The employee's department.
 */
function assign (employees) {

};
// Message: @param path declaration ("employees[].name") appears before any real parameter.

/**
 * Assign the project to a list of employees.
 * @param {string} employees[].name - The name of an employee.
 * @param {string} employees[].name - The employee's department.
 */
function assign (employees) {

};
// Message: Duplicate @param "employees[].name"

/**
 * @param foo
 * @param foo.bar
 * @param bar
 */
function quux (bar, foo) {

}
// Message: Expected @param names to be "bar, foo". Got "foo, bar".

/**
 * @param foo
 * @param bar
 */
function quux (foo) {

}
// Message: @param "bar" does not match an existing function parameter.

/**
 * @param foo
 * @param foo
 */
function quux (foo) {

}
// Message: Duplicate @param "foo"

/**
 * @param foo
 * @param foo
 */
function quux (foo, bar) {

}
// Message: Duplicate @param "foo"

/**
 * @param foo
 * @param foo
 */
function quux (foo, foo) {

}
// Message: Duplicate @param "foo"

/**
 * @param cfg
 * @param cfg.foo
 * @param cfg.foo
 */
function quux ({foo, bar}) {

}
// Message: Duplicate @param "cfg.foo"

/**
 * @param cfg
 * @param cfg.foo
 * @param [cfg.foo]
 * @param baz
 */
function quux ({foo, bar}, baz) {

}
// Message: Duplicate @param "cfg.foo"

/**
 * @param cfg
 * @param cfg.foo
 * @param [cfg.foo="with a default"]
 * @param baz
 */
function quux ({foo, bar}, baz) {

}
// Message: Duplicate @param "cfg.foo"

export class SomeClass {
  /**
   * @param prop
   */
  constructor(private property: string) {}
}
// Message: Expected @param names to be "property". Got "prop".

/**
 * @param foo
 */
function quux (foo) {

}
// Settings: {"jsdoc":{"tagNamePreference":{"param":false}}}
// Message: Unexpected tag `@param`

/**
 * @param {Error} error Exit code
 * @param {number} [code = 1] Exit code
 */
function quux (error, cde = 1) {
};
// Message: Expected @param names to be "error, cde". Got "error, code".
````

The following patterns are not considered problems:

````js
/**
 *
 */
function quux (foo) {

}

/**
 * @param foo
 */
function quux (foo) {

}

/**
 * @param foo
 * @param bar
 */
function quux (foo, bar) {

}

/**
 * @param foo
 * @param bar
 */
function quux (foo, bar, baz) {

}

/**
 * @param foo
 * @param foo.foo
 * @param bar
 */
function quux (foo, bar) {

}

/**
 * @param args
 */
function quux (...args) {

}

/**
 * @param foo
 */
function quux ({a, b}) {

}

/**
 * @param foo
 * @param foo.bar
 * @param foo.baz
 * @param bar
 */
function quux (foo, bar) {

}

/**
 * @param args
 */
function quux ({a, b} = {}) {

}

/**
 * @param foo
 */
function quux ([a, b] = []) {

}

/**
 * Assign the project to a list of employees.
 * @param {object[]} employees - The employees who are responsible for the project.
 * @param {string} employees[].name - The name of an employee.
 * @param {string} employees[].department - The employee's department.
 */
function assign (employees) {

};

export class SomeClass {
  /**
   * @param property
   */
  constructor(private property: string) {}
}

/**
 * @param {Error} error Exit code
 * @param {number} [code = 1] Exit code
 */
function quux (error, code = 1) {
};

/**
 * @param foo
 * @param bar
 */
function quux (foo) {

}
// Options: [{"allowExtraTrailingParamDocs":true}]
````


<a name="eslint-plugin-jsdoc-rules-check-param-names-deconstructing-function-parameter"></a>
#### Deconstructing Function Parameter

`eslint-plugin-jsdoc` does not validate names of parameters in function deconstruction, e.g.

```js
/**
 * @param foo
 */
function quux ({
    a,
    b
}) {

}
```

`{a, b}` is an [`ObjectPattern`](https://github.com/estree/estree/blob/master/es2015.md#objectpattern) AST type and does not have a name. Therefore, the associated parameter in JSDoc block can have any name.

Likewise for the pattern `[a, b]` which is an [`ArrayPattern`](https://github.com/estree/estree/blob/master/es2015.md#arraypattern).

<a name="eslint-plugin-jsdoc-rules-check-property-names"></a>

## Further Reading

* [eslint-plugin-jsdoc - check-param-names](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#check-param-names)
