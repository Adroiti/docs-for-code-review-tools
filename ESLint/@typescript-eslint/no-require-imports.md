Pattern: CommonJS require() usage

Issue: -

## Description

Using require() imports instead of ES6 import syntax reduces code consistency and prevents static analysis tools from properly understanding module dependencies. It also makes it harder to use modern JavaScript features and optimizations like tree shaking.

## Examples

Example of **incorrect** code:
```ts
// require with assignment
const fs = require('fs');
const { join } = require('path');

// require in type imports
import MyType = require('./types');

// Dynamic require
const config = process.env.NODE_ENV === 'production'
  ? require('./prod.config')
  : require('./dev.config');

// require in variable declarations
var util = require('util');
let debug = require('debug');

// Nested require
const helper = {
  tool: require('./tool')
};
```

Example of **correct** code:
```ts
// ES6 imports
import * as fs from 'fs';
import { join } from 'path';

// Type imports
import type { MyType } from './types';

// Dynamic imports
const config = await import(
  process.env.NODE_ENV === 'production'
    ? './prod.config'
    : './dev.config'
);

// Namespace imports
import * as util from 'util';
import * as debug from 'debug';

// Named imports
import { tool } from './tool';

// Default imports
import defaultThing from './thing';

// Side effect imports
import './polyfills';
```