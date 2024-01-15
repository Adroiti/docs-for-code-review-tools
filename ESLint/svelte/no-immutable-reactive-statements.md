Pattern: Use of immutable reactive statement

Issue: -

## Description

This rule reports if all variables referenced in reactive statements are immutable. That reactive statement is immutable and not reactive.

```svelte
<script>
  /* eslint svelte/no-immutable-reactive-statements: "error" */
  import myStore from './my-stores';
  import myVar from './my-variables';
  let mutableVar = 'hello';
  export let prop;
  /* ✓ GOOD */
  $: computed1 = mutableVar + ' ' + mutableVar;
  $: computed2 = fn1(mutableVar);
  $: console.log(mutableVar);
  $: console.log(computed1);
  $: console.log($myStore);
  $: console.log(prop);

  const immutableVar = 'hello';
  /* ✗ BAD */
  $: computed3 = fn1(immutableVar);
  $: computed4 = fn2();
  $: console.log(immutableVar);
  $: console.log(myVar);

  /* ignore */
  $: console.log(unknown);

  function fn1(v) {
    return v + ' ' + v;
  }
  function fn2() {
    return mutableVar + ' ' + mutableVar;
  }
</script>

<input bind:value={mutableVar} />
```

## :wrench: Options

Nothing.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.27.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/no-immutable-reactive-statements.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/no-immutable-reactive-statements.ts)
