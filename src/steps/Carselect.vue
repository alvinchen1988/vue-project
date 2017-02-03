<template>
  <div class="car-select">
      <h1>{{title}}}</h1>
      <buttonlist :buttonDescriptions=monthlyBudgets></buttonlist>
  </div>
</template>

<script>

import Buttonlist from '../components/Buttonlist'

export default {
  name: 'carselect',
  components: {
    Buttonlist
  },
  data () {
    return {
      title: 'Select Your Monthly Budget',
      monthlyBudgets: [
        {
          amount: 'Under $250 / month'
        },
        {
          amount: '$250 - 375 / month'
        },
        {
          amount: '$376 - 500 / month'
        },
        {
          amount: '$501+ / month'
        }
      ],
      selected: ''
    }
  },
  methods: {

  },
  computed: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.active{
  background-color: blue;
}
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
