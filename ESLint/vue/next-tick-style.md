Pattern: Malformed `Vue.nextTick`/`this.$nextTick`

Issue: -

## Description

Enforces whether the callback version or Promise version (which was introduced in Vue v2.1.0) should be used in `Vue.nextTick` and `this.$nextTick`.

```vue
<script>
import { nextTick as nt } from 'vue';

export default {
  async mounted() {
    /* ✓ GOOD */
    nt().then(() => callback());
    await nt(); callback();
    Vue.nextTick().then(() => callback());
    await Vue.nextTick(); callback();
    this.$nextTick().then(() => callback());
    await this.$nextTick(); callback();

    /* ✗ BAD */
    nt(() => callback());
    nt(callback);
    Vue.nextTick(() => callback());
    Vue.nextTick(callback);
    this.$nextTick(() => callback());
    this.$nextTick(callback);
  }
}
</script>
```

## Further Reading

* [eslint-plugin-vue - next-tick-style](https://eslint.vuejs.org/rules/next-tick-style.html)
