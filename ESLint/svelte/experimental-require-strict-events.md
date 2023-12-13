Pattern: Missing use of `strictEvents` on `<script>` tag

Issue: -

## Description

This rule enforces the presence of the `strictEvents` attribute on the main `<script>` tag of all components. This attributes enforces type-checking of events dispatched by the component, e.g. making it a typescript error to listen to any non-existent events. Alternatively, the event types may be defined manually by declaring the `$$Events` interface.

The `strictEvents` attribute and the `$$Events` interface are experimental and are documented in [svelte RFC #38](https://github.com/dummdidumm/rfcs/blob/ts-typedefs-within-svelte-components/text/ts-typing-props-slots-events.md#typing-events).

```svelte
<!-- ✓ GOOD -->
<script lang="ts" strictEvents>
  /* eslint svelte/experimental-require-strict-events: "error" */
</script>
```

```svelte
<!-- ✓ GOOD -->
<script lang="ts">
  /* eslint svelte/experimental-require-strict-events: "error" */
  interface $$Events {}
</script>
```

```svelte
<!-- ✗ BAD -->
<script lang="ts">
  /* eslint svelte/experimental-require-strict-events: "error" */
</script>
```

## :wrench: Options

Nothing.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.18.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/experimental-require-strict-events.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/experimental-require-strict-events.ts)
