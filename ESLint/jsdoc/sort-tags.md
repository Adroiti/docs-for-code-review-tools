Pattern: Wrong tag order

Issue: -

## Description

Sorts tags by a specified sequence according to tag name.

The following patterns are considered problems:

```js
/**
 * @returns {string}
 * @param b
 * @param a
 */
function quux () {}
// Message: Tags are not in the prescribed order: summary, typeSummary, module, exports, file, fileoverview, overview, typedef, interface, record, template, name, kind, type, alias, external, host, callback, func, function, method, class, constructor, modifies, mixes, mixin, mixinClass, mixinFunction, namespace, borrows, constructs, lends, implements, requires, desc, description, classdesc, tutorial, copyright, license, internal, const, constant, final, global, readonly, abstract, virtual, var, member, memberof, memberof!, inner, instance, inheritdoc, inheritDoc, override, hideconstructor, param, arg, argument, prop, property, return, returns, async, generator, default, defaultvalue, enum, augments, extends, throws, exception, yield, yields, event, fires, emits, listens, this, static, private, protected, public, access, package, -other, see, example, closurePrimitive, customElement, expose, hidden, idGenerator, meaning, ngInject, owner, wizaction, define, dict, export, externs, implicitCast, noalias, nocollapse, nocompile, noinline, nosideeffects, polymer, polymerBehavior, preserve, struct, suppress, unrestricted, category, ignore, author, version, variation, since, deprecated, todo

/**
 * Some description
 * @returns {string}
 * @param b
 * @param a
 */
function quux () {}
// Message: Tags are not in the prescribed order: summary, typeSummary, module, exports, file, fileoverview, overview, typedef, interface, record, template, name, kind, type, alias, external, host, callback, func, function, method, class, constructor, modifies, mixes, mixin, mixinClass, mixinFunction, namespace, borrows, constructs, lends, implements, requires, desc, description, classdesc, tutorial, copyright, license, internal, const, constant, final, global, readonly, abstract, virtual, var, member, memberof, memberof!, inner, instance, inheritdoc, inheritDoc, override, hideconstructor, param, arg, argument, prop, property, return, returns, async, generator, default, defaultvalue, enum, augments, extends, throws, exception, yield, yields, event, fires, emits, listens, this, static, private, protected, public, access, package, -other, see, example, closurePrimitive, customElement, expose, hidden, idGenerator, meaning, ngInject, owner, wizaction, define, dict, export, externs, implicitCast, noalias, nocollapse, nocompile, noinline, nosideeffects, polymer, polymerBehavior, preserve, struct, suppress, unrestricted, category, ignore, author, version, variation, since, deprecated, todo

```

The following patterns are not considered problems:

```js
/**
 * @param b
 * @param a
 * @returns {string}
 */
function quux () {}

/**
 * @abc
 * @def
 * @xyz
 */
function quux () {}
// "jsdoc/sort-tags": ["error"|"warn", {"alphabetizeExtras":true}]

/**
 * @def
 * @xyz
 * @abc
 */
function quux () {}
// "jsdoc/sort-tags": ["error"|"warn", {"alphabetizeExtras":false}]

/**
 * @def
 * @xyz
 * @abc
 */
function quux () {}
// "jsdoc/sort-tags": ["error"|"warn", {"tagSequence":["def","xyz","abc"]}]

/** @def */
function quux () {}
```


## Further Reading

* [eslint-plugin-jsdoc - require-param](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#require-param)
