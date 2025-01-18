Pattern: Variable declaration without initialization

Issue: -

## Description

Variables declared without initialization can lead to potential undefined behavior and make code intent less clear. Each variable should be initialized at the time of declaration unless there's a specific reason not to do so.

## Examples

Example of **incorrect** code:
```ts
let name;
name = 'John';

var age;
age = 25;

let user: User;
user = loadUser();

// Multiple declarations without initialization
let x, y, z;
x = 1;
y = 2;
z = 3;
```

Example of **correct** code:
```ts
let name = 'John';
const age = 25;

// Initialization with appropriate value
let user: User = loadUser();

// Multiple declarations with initialization
let x = 1, y = 2, z = 3;

// Declared variables are exempt when necessary
declare let external: string;

// Initialization with placeholder if actual value comes later
let status = '';
status = computeStatus();
```