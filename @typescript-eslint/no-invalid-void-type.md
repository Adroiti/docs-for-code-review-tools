Pattern: Misused void type annotation

Issue: -

## Description

The void type in TypeScript represents the absence of a return value from a function. Using void in other contexts, such as type unions or variable types, can be misleading and often indicates a misunderstanding of its purpose. When needing to represent "no value," undefined is typically more appropriate.

## Examples

Example of **incorrect** code:
```ts
// void in unions
type Result = string | void;
type Status = number | void | null;

// void as parameter type
function process(value: void) {}

// void as property type
interface Config {
  name: string;
  value: void;
}

// void in generics (when configured)
type Container<T = void> = {
  data: T;
};

// void in class property
class Example {
  private data: void;
}

// void in array type
type VoidArray = void[];
```

Example of **correct** code:
```ts
// void in function return
function logMessage(msg: string): void {
  console.log(msg);
}

// void in arrow function
const log = (): void => {
  console.log('message');
};

// void in Promise generic
async function process(): Promise<void> {
  await doWork();
}

// void in callback type
type Callback = () => void;

// undefined for optional values
type Result = string | undefined;

// null for intentionally empty values
interface Config {
  name: string;
  value: null;
}

// this parameter type annotation
function handler(this: void) {}
```