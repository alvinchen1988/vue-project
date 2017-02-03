<template>
    {{ selected }}
    <button @click=toggleStatus>{{text}}></button>

</template>

<script>
export default {
  name: 'uibutton',
  props: ['text', 'selected'],
  data () {
    return {
    }
  },
  methods: {
    toggleStatus: function () {
      this.$emit('resetButton', this.$el)
      // this.$nextTick(() => {
      // this.selected = true

      // })
    }
  },
  computed: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.active{
  background-color: green;
}

</style>
