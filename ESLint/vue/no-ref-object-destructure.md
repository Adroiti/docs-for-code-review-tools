Pattern: Destructuring ref object

Issue: -

## Description

This rule reports the destructuring of ref objects causing the value to lose reactivity.

```vue
import { ref } from 'vue'
const count = ref(0)
const v1 = count.value /* ✗ BAD */
const { value: v2 } = count /* ✗ BAD */
const v3 = computed(() => count.value /* ✓ GOOD */)
const v4 = fn(count.value) /* ✗ BAD */
const v5 = fn(count) /* ✓ GOOD */
const v6 = computed(() => fn(count.value) /* ✓ GOOD */)
```

## Further Reading

* [eslint-plugin-vue - no-ref-object-destructure](https://eslint.vuejs.org/rules/no-ref-object-destructure.html)
