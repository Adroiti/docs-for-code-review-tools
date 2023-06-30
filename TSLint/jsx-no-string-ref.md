Pattern: Passing string to `ref` prop

Issue: -

## Description

Passing strings to the `ref` prop of React elements is considered a legacy feature and will soon be deprecated. Instead, use a callback.

Example of **incorrect** code:

```ts
a = <div ref="value"></div>
             ~~~~~~~
```

Example of **correct** code:

```ts
a = <div ref={this.handleRef}/>
```