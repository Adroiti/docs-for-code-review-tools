Pattern: Use of computed property like method

Issue: -

## Description

Disallows to use computed property like method.

```vue
<script>
export default {
  data() {
    return {
      dataString: 'dataString',
      dataNumber: 10,
      dataObject: {
        inside: 'inside'
      },
      dataArray: [1, 2, 3, 4, 5],
      dataBoolean: true,
      dataFunction() {
        alert('dataFunction')
      }
    }
  },
  props: {
    propsString: String,
    propsNumber: Number,
    propsObject: Object,
    propsArray: Array,
    propsBoolean: Boolean,
    propsFunction: Function,

    objectPropsString: {
      type: String
    },
    objectPropsNumber: {
      type: Number
    },
    objectPropsObject: {
      type: Object
    },
    objectPropsArray: {
      type: Array
    },
    objectPropsBoolean: {
      type: Boolean
    },
    objectPropsFunction: {
      type: Function
    }
  },
  computed: {
    computedReturnDataString() {
      return this.dataString
    },
    computedReturnDataNumber() {
      return this.dataNumber
    },
    computedReturnDataObject() {
      return this.dataObject
    },
    computedReturnDataArray() {
      return this.dataArray
    },
    computedReturnDataBoolean() {
      return this.dataBoolean
    },
    computedReturnDataFunction() {
      return this.dataFunction
    },

    computedReturnPropsString() {
      return this.propsString
    },
    computedReturnPropsNumber() {
      return this.propsNumber
    },
    computedReturnPropsObject() {
      return this.propsObject
    },
    computedReturnPropsArray() {
      return this.propsArray
    },
    computedReturnPropsBoolean() {
      return this.propsBoolean
    },
    computedReturnPropsFunction() {
      return this.propsFunction
    },

    computedReturnObjectPropsString() {
      return this.objectPropsString
    },
    computedReturnObjectPropsNumber() {
      return this.objectPropsNumber
    },
    computedReturnObjectPropsObject() {
      return this.objectPropsObject
    },
    computedReturnObjectPropsArray() {
      return this.objectPropsArray
    },
    computedReturnObjectPropsBoolean() {
      return this.objectPropsBoolean
    },
    computedReturnObjectPropsFunction() {
      return this.objectPropsFunction
    },

    computedReturnString() {
      return 'computedReturnString'
    },
    computedReturnNumber() {
      return 10
    },
    computedReturnObject() {
      return {
        inside: 'inside'
      }
    },
    computedReturnArray() {
      return [1, 2, 3, 4, 5]
    },
    computedReturnBoolean() {
      return true
    },
    computedReturnFunction() {
      const fn = () => alert('computedReturnFunction')
      return fn
    },

    computedReturnMethodsReturnString() {
      return this.methodsReturnString
    },
    computedReturnMethodsReturnNumber() {
      return this.methodsReturnNumber
    },
    computedReturnMethodsReturnObject() {
      return this.methodsReturnObject
    },
    computedReturnMethodsReturnArray() {
      return this.methodsReturnArray
    },
    computedReturnMethodsReturnBoolean() {
      return this.methodsReturnBoolean
    },
    computedReturnMethodsReturnFunction() {
      return this.methodsReturnFunction
    }
  },
  methods: {
    methodsReturnString() {
      return 'methodsReturnString'
    },
    methodsReturnNumber() {
      return 'methodsReturnNumber'
    },
    methodsReturnObject() {
      return {
        inside: 'inside'
      }
    },
    methodsReturnArray() {
      return [1, 2, 3, 4, 5]
    },
    methodsReturnBoolean() {
      return true
    },
    methodsReturnFunction() {
      const fn = () => alert('methodsReturnFunction')
      return fn
    },

    fn() {
      /* Reference data */
      /* ✓ GOOD */
      this.computedReturnDataString
      this.computedReturnDataNumber
      this.computedReturnDataObject
      this.computedReturnDataArray
      this.computedReturnDataBoolean
      this.computedReturnDataFunction
      this.computedReturnDataFunction()
      /* ✗ BAD */
      this.computedReturnDataString()
      this.computedReturnDataNumber()
      this.computedReturnDataObject()
      this.computedReturnDataArray()
      this.computedReturnDataBoolean()

      /* Reference props */
      /* ✓ GOOD */
      this.computedReturnPropsString
      this.computedReturnPropsNumber
      this.computedReturnPropsObject
      this.computedReturnPropsArray
      this.computedReturnPropsBoolean
      this.computedReturnPropsFunction
      this.computedReturnPropsFunction()
      /* ✗ BAD */
      this.computedReturnPropsString()
      this.computedReturnPropsNumber()
      this.computedReturnPropsObject()
      this.computedReturnPropsArray()
      this.computedReturnPropsBoolean()

      /* ✓ GOOD */
      this.computedReturnObjectPropsString
      this.computedReturnObjectPropsNumber
      this.computedReturnObjectPropsObject
      this.computedReturnObjectPropsArray
      this.computedReturnObjectPropsBoolean
      this.computedReturnObjectPropsFunction
      this.computedReturnObjectPropsFunction()
      /* ✗ BAD */
      this.computedReturnObjectPropsString()
      this.computedReturnObjectPropsNumber()
      this.computedReturnObjectPropsObject()
      this.computedReturnObjectPropsArray()
      this.computedReturnObjectPropsBoolean()

      /* Reference computed */
      /* ✓ GOOD */
      this.computedReturnString
      this.computedReturnNumber
      this.computedReturnObject
      this.computedReturnArray
      this.computedReturnBoolean
      this.computedReturnFunction
      this.computedReturnFunction()
      /* ✗ BAD */
      this.computedReturnString()
      this.computedReturnNumber()
      this.computedReturnObject()
      this.computedReturnArray()
      this.computedReturnBoolean()

      /* Reference methods */
      /* ✓ GOOD */
      this.computedReturnMethodsReturnString
      this.computedReturnMethodsReturnNumber
      this.computedReturnMethodsReturnObject
      this.computedReturnMethodsReturnArray
      this.computedReturnMethodsReturnBoolean
      this.computedReturnMethodsReturnFunction
      this.computedReturnMethodsReturnFunction()
      /* ✗ BAD */
      this.computedReturnMethodsReturnString()
      this.computedReturnMethodsReturnNumber()
      this.computedReturnMethodsReturnObject()
      this.computedReturnMethodsReturnArray()
      this.computedReturnMethodsReturnBoolean()
    }
  }
}
</script>

```

## Further Reading

* [eslint-plugin-vue - no-use-computed-property-like-method](https://eslint.vuejs.org/rules/no-use-computed-property-like-method.html)
