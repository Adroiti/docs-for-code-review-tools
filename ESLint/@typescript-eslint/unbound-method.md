Pattern: Unbound method reference

Issue: -

## Description

When class methods are passed around as standalone values without being bound to their class instance, they lose their `this` context. This can cause runtime errors as the method may try to access instance properties or methods through `this` when called, but `this` will be undefined or point to the global scope.

## Examples

Example of **incorrect** code:
```ts
class Logger {
  prefix: string = '>';
  
  log(text: string) {
    console.log(this.prefix, text);
  }
}

const logger = new Logger();

// Loses this context
const logFn = logger.log;
logFn('test');

// Destructuring also loses context
const { log } = logger;
log('test');

// Passing as callback loses context
['message'].forEach(logger.log);
```

Example of **correct** code:
```ts
class Logger {
  prefix: string = '>';
  
  // Arrow function automatically binds
  log = (text: string) => {
    console.log(this.prefix, text);
  }

  // Explicitly declare no this usage
  static format(this: void, text: string) {
    return `[${text}]`;
  }
}

const logger = new Logger();

// These preserve the this context
const boundLog = logger.log.bind(logger);
const wrapLog = (text: string) => logger.log(text);

// Static method doesn't need this
const { format } = Logger;
```