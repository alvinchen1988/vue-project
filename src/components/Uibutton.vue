<template>
    <button :class="{'active': selected}"
    @click="$emit('click', text)">{{text}}></button>
</template>

<script>
export default {
  name: 'uibutton',
  props: ['text', 'selected'],
  // data () {
  //   return {
  //   }
  // },
  // methods: {
  //   toggleStatus: function () {
  //     this.$emit('select', this.$el)
  //     // this.$emit('select', this.$el)
  //     // this.$nextTick(() => {
  //     // this.selected = true

  //     // })
  //   }
  // },
  // computed: {
  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.active{
  background-color: green;
}

</style>
