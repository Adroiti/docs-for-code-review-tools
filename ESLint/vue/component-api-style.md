Pattern: Inconsistent consistent API style

Issue: -

## Description

This rule aims to make the API style you use to define Vue components consistent in your project.

For example, if you want to allow only `<script setup>` and Composition API.
(This is the default for this rule.)

```vue
<!-- ✓ GOOD -->
<script setup>
import { ref } from 'vue'
const msg = ref('Hello World!')
</script>

<script>
import { ref } from 'vue'
export default {
  /* ✓ GOOD */
  setup() {
    const msg = ref('Hello World!')
    // ...
    return {
      msg,
      // ...
    }
  }
}
</script>

<script>
export default {
  /* ✗ BAD */
  data () {
    return {
      msg: 'Hello World!',
      // ...
    }
  },
  // ...
}
</script>
```


## Further Reading

* [eslint-plugin-vue - component-api-style](https://eslint.vuejs.org/rules/component-api-style.html)
