<template>

  <div class="button-list">

    <div v-for="(button, index) in buttonDescriptions">
      <uibutton :text="button.amount"
      :selected="index === selectedIndex"
      @click="selectButton($event, index)">
      </uibutton>
    </div>

  </div>

</template>

<script>

import Uibutton from './Uibutton'

export default {
  name: 'buttonlist',
  props: ['buttonDescriptions'],
  components: {
    Uibutton
  },

  // mounted () {
  //   console.log(this.$refs.buttons)
  // },

  data () {
    return {
      selectedIndex: undefined
    }
  },
  methods: {
    selectButton (text, index) {
      this.selectedIndex = index
      this.$emit('select', text)
    }
    // resetSelected: function(index, element){

    //   var text = element.innerText;

    //   this.buttonDescriptions.forEach(function(description){
    //       if(description.amount === description){
    //         this.selected = description;
    //       }
    //   });

    //   // if (this.selected) {
    //   //   this.$refs.buttons[this.selected].classList.remove('active')
    //   // }
    //   // console.log(element)
    //   // element.classList.add('active')
    //   // this.selected = index
    //   //this.$refs.buttons[index].classList.add('active')
    //   //this.selected
    // }

  },
  // computed: {

  //   buttons: function(){
  //     return this.buttonDescriptions.map(function(item, index){
  //       item.selected = true
  //       //this.$set(this.buttonDescriptions, index, item)
  //       return item
  //     })
  //   }

  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.active{
  background-color: green;
}

</style>
