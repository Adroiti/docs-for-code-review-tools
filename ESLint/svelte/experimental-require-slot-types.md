Pattern: Missing slot type declaration using `$$Slots` interface

Issue: -

## Description

This rule enforces the presence of the `$$Slots` interface if any slots are present in the component. This interface declares all of the used slots and their props and enables type-checking both in the component itself as well as all components that include it.

The `$$Slots` interface is experimental and is documented in [svelte RFC #38](https://github.com/dummdidumm/rfcs/blob/ts-typedefs-within-svelte-components/text/ts-typing-props-slots-events.md#typing-slots).

```svelte
<!-- ✓ GOOD -->
<script lang="ts">
  /* eslint svelte/experimental-require-slot-types: "error" */
</script>

<b>No slots here!</b>
```

```svelte
<!-- ✓ GOOD -->
<script lang="ts">
  /* eslint svelte/experimental-require-slot-types: "error" */

  interface $$Slots {
    default: Record<string, never>;
  }
</script>

<slot />
```

```svelte
<!-- ✓ GOOD -->
<script lang="ts">
  /* eslint svelte/experimental-require-slot-types: "error" */

  interface $$Slots {
    default: { prop: boolean };
  }
</script>

<slot prop={true} />
```

```svelte
<!-- ✓ GOOD -->
<script lang="ts">
  /* eslint svelte/experimental-require-slot-types: "error" */

  interface $$Slots {
    named: Record<string, never>;
  }
</script>

<slot name="named" />
```

```svelte
<!-- ✗ BAD -->
<script lang="ts">
  /* eslint svelte/experimental-require-slot-types: "error" */
</script>

<slot />
```

## :wrench: Options

Nothing.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.18.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/experimental-require-slot-types.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/experimental-require-slot-types.ts)
