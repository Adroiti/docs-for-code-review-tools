Pattern: String evaluation via indirect eval method

Issue: -

## Description

Using methods that evaluate strings as code (setTimeout, setInterval, setImmediate, execScript, new Function) creates the same security and performance risks as eval(). These methods are often overlooked when restricting eval-like behavior.

## Examples

Example of **incorrect** code:
```ts
// String execution in timeouts
setTimeout('alert("Hello!");', 100);
setInterval('console.log("tick");', 1000);

// String execution in immediate callbacks
setImmediate('performTask();');

// Browser-specific string execution
execScript('var x = 10;');

// String to function conversion
const add = new Function('a', 'b', 'return a + b');

// Dynamic function strings
const handler = 'alert("clicked")';
setTimeout(handler, 100);

// Function return value as string
const getCode = () => 'doSomething()';
setInterval(getCode(), 1000);
```

Example of **correct** code:
```ts
// Function references in timeouts
setTimeout(() => {
  alert("Hello!");
}, 100);

setInterval(function tick() {
  console.log("tick");
}, 1000);

// Direct function execution
setImmediate(() => performTask());

// Function definition without string eval
const add = (a: number, b: number) => a + b;

// Function references
const handler = () => alert("clicked");
setTimeout(handler, 100);

// Component methods
class Component {
  tick = () => console.log("tick");
  start() {
    setInterval(this.tick, 1000);
  }
}

// Bound methods
const obj = {
  task() { console.log("task"); }
};
setTimeout(obj.task.bind(obj), 100);
```