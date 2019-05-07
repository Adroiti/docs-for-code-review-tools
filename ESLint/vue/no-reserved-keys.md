Pattern: no reserved keys

Issue: -

## Description

This rule prevents to use [reserved names](https://github.com/vuejs/eslint-plugin-vue/blob/master/lib/utils/vue-reserved.json) to avoid conflicts and unexpected behavior.

<eslint-code-block :rules="{'vue/no-reserved-keys': ['error']}">

```vue
<script>
/* ✗ BAD */
export default {
  props: {
    $el: String
  },
  computed: {
    $on: {
      get () {}
    }
  },
  data: {
    _foo: null
  },
  methods: {
    $nextTick () {}
  }
}
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-reserved-keys": ["error", {
    "reserved": [],
    "groups": []
  }]
}
```

- `reserved` (`string[]`) ... Array of additional restricted attributes inside `groups`. Default is empty.
- `groups` (`string[]`) ... Array of additional group names to search for duplicates in. Default is empty.

### `"reserved": ["foo", "foo2"], "groups": ["firebase"]`

<eslint-code-block :rules="{'vue/no-reserved-keys': ['error', {reserved: ['foo', 'foo2'], groups: ['firebase']}]}">

```vue
<script>
/* ✗ BAD */
export default {
  computed: {
    foo () {}
  },
  firebase: {
    foo2 () {}
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-reserved-keys](https://eslint.vuejs.org/rules/no-reserved-keys.html)
