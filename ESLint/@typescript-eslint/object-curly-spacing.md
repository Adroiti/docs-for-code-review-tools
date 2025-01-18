Pattern: Inconsistent spacing in curly braces

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent spacing inside object literal curly braces and TypeScript type braces, which can now be configured using the stylistic plugin's object-curly-spacing rule.

## Examples

Example of **incorrect** code:
```ts
const obj = {foo: 'bar'};
const {foo,bar} = obj;
import {foo,bar} from 'module';

type Props = {name: string};
interface Options {timeout: number};
```

Example of **correct** code:
```ts
const obj = { foo: 'bar' };
const { foo, bar } = obj;
import { foo, bar } from 'module';

type Props = { name: string };
interface Options { timeout: number };

// Alternative style (no spaces)
const obj = {foo: 'bar'};
const {foo, bar} = obj;
type Props = {name: string};
```

See [eslint.style](https://eslint.style) for the current version of this rule.