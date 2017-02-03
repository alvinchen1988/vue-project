<template>
  <div class="car-select">
      <h1>{{title}}</h1>
      <buttonlist :buttonDescriptions="monthlyBudgets"
      @select="setSelected($event)">
      </buttonlist>
      <p v-if="selected">{{ selected }}</p>
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
          amount: 'Under $250 / month',
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
      selected: undefined
    }
  },
  methods: {
    // Set the selected button
    setSelected (text) {
      this.selected = text
      // Check if something is already selected
      // if (this.selected) {
      //   this.selected.selected = false
      // }

      // // use $set because 'selected' may not be tracked by Vue yet
      // // equivilent to: this.monthlyBudgets[index].selected = true
      // this.$set(this.monthlyBudgets[index], 'selected', true)
      // this.selected = this.monthlyBudgets[index]
    }
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
