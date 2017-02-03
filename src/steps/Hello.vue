<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <input type="text" v-model="firstName">
    <input type="text" v-model="lastName">
    <h1>My full name is {{fullName}}</h1>
    <p>{{printSomething}}</p>
  </div>

</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Hello! Alvins first Vue App',
      firstName: 'Tony',
      lastName: 'Nikkalas'
    }
  },
  methods: {
    logSomething: function (e) {
      e.preventDefault()
      console.log('hello')
    },
    printSomething: function () {
      return this.$root.$data
    }
  },
  computed: {
    fullName: function () {
      return this.firstName + ' ' + this.lastName
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
