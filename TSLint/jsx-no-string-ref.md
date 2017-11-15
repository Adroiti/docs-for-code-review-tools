Pattern: Passing string to `ref` prop

Issue: -

## Description

Passing strings to the `ref` prop of React elements is considered a legacy feature and will soon be deprecated. Instead, [use a callback](https://facebook.github.io/react/docs/more-about-refs.html#the-ref-callback-attribute).

Example of **incorrect** code:

```ts
a = <div ref="value"></div>
             ~~~~~~~
```

Example of **correct** code:

```ts
a = <div ref={this.handleRef}/>
```