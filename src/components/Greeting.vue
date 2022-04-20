<template>
  <p>{{msg}}</p>
  <button @click="onClickAge">
  Inc. Age from Child comp using Emit Event
  </button>
  <button @click="ageChangeFun(3)">
  Inc. Age from Child comp using Function
  </button>
</template>

<script>
export default {
  name: "Greeting-Comp",
  props: {
    age: {
      type: Number,
      required: true
    },
    username: {
      type: String
    },
    ageChangeFun: Function
  },
  emits: ['increase-age'],
  data() {
    return {
      msg: "You must be 21 years or older to view this message",
      greet: "Hellooo",
    }
  },
  methods: {
    onClickAge () {
      this.$emit('increase-age', 2)
    }
  }
}
</script>

<style scoped>
p {
  color: red;
}
</style>
