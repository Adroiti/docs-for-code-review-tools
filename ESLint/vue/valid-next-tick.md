Pattern: Invalid call to `Vue.nextTick`/`vm.$nextTick`

Issue: -

## Description

Calling `Vue.nextTick` or `vm.$nextTick` without passing a callback and without awaiting the returned Promise is likely a mistake (probably a missing `await`).

```vue
<script>
import { nextTick as nt } from 'vue';

export default {
  async mounted() {
    /* ✗ BAD: no callback function or awaited Promise */
    nt();
    Vue.nextTick();
    this.$nextTick();

    /* ✗ BAD: too many parameters */
    nt(callback, anotherCallback);
    Vue.nextTick(callback, anotherCallback);
    this.$nextTick(callback, anotherCallback);

    /* ✗ BAD: no function call */
    nt.then(callback);
    Vue.nextTick.then(callback);
    this.$nextTick.then(callback);
    await nt;
    await Vue.nextTick;
    await this.$nextTick;

    /* ✗ BAD: both callback function and awaited Promise */
    nt(callback).then(anotherCallback);
    Vue.nextTick(callback).then(anotherCallback);
    this.$nextTick(callback).then(anotherCallback);
    await nt(callback);
    await Vue.nextTick(callback);
    await this.$nextTick(callback);

    /* ✓ GOOD */
    await nt();
    await Vue.nextTick();
    await this.$nextTick();

    /* ✓ GOOD */
    nt().then(callback);
    Vue.nextTick().then(callback);
    this.$nextTick().then(callback);

    /* ✓ GOOD */
    nt(callback);
    Vue.nextTick(callback);
    this.$nextTick(callback);
  }
}
</script>
```

## Further Reading

* [eslint-plugin-vue - valid-next-tick](https://eslint.vuejs.org/rules/valid-next-tick.html)
