Pattern: Use of relative path for aliased module

Issue: -

## Description

Allows you to enforce that aliased modules are not using relative paths.

## Rule Details

Given the babel configuration below

```json
...
  "plugins": [
    [
      "module-resolver",
      {
        "root": ["."],
        "alias": {
          "action": "./actions"
        }
      }
    ]
  ]
...
```

The following patterns are considered warnings:

```js
import fetchData from '../../actions/fetchData'
```

```js
const fetchData = require('../../actions/fetchData')
```

```js
const fetchData = await import('../../actions/fetchData')
```

The following patterns are **not** considered warnings:

```js
import fetchData from 'actions/fetchData'
```

```js
const fetchData = require('actions/fetchData')
```

```js
const fetchData = await import('actions/fetchData')
```

## Further Reading

* [GitHub - use-alias](https://github.com/HeroProtagonist/eslint-plugin-module-resolver/blob/HEAD/docs/rules/use-alias.md)