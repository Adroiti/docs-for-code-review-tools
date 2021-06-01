Pattern: Wrong module import order

Issue: -

## Description

Enforces a convention in the order of `require()`/`import` statements. The default order is as shown in the following example:

```js
// 1. "absolute" path modules
import abs from '/absolute-module'; // uncommon
// 2. all non-relative and non-absolute "modules"
import fs from 'fs';
import path from 'path';
import _ from 'lodash';
import chalk from 'chalk';
import foo from 'src/foo';
// 3. modules from a "parent" directory
import foo from '../foo';
import qux from '../../foo/qux';
// 4. "sibling" modules from the same or a sibling's directory
import bar from './bar';
import baz from './bar/baz';
// 5. "index" of the current directory
import main from './';
```

## Further Reading

* [GitHub - order-imports](https://github.com/Tibfib/eslint-plugin-import-helpers/blob/master/docs/rules/order-imports.md)