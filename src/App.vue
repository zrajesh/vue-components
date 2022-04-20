<template>
  <p>{{msg}}</p>
  <GreetingComp
   :age="age" 
   :username="username" 
   @increase-age="updateAge" 
   :ageChangeFun="updateAgeCallBack"
  />
  <user-vue :age="age" />

  <p v-if="age >= 21">{{greet}} {{username}}</p>
  
  <button @click="age++">Increase age</button>
  <button @click="age--">Decrease age</button>
</template>

<script>
import GreetingComp from './components/Greeting.vue'
import UserVue from './components/User.vue'

export default {
  name: "App",
  components: {
    GreetingComp,
    UserVue
  },
  data() {
    return {
      msg: "HELLOOOOOOOOOOO! VUE",
      age: 20,
      username: "Mr. X",
      greet: "Hello"
    }
  },
  methods: {
    updateAge(increment_number) {
      this.age += increment_number;
    },
    updateAgeCallBack(num) {
      this.age += num;
    }
  }
}
</script>

<style>
p {
  color: blue;
}
</style>

