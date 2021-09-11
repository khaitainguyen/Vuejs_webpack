<template lang="">
  <div>
    <h1>{{ text }} </h1>
    <p> {{ titleHeader }}</p>
    <button v-on:click="changeTitleHeader">Change title</button>
  </div>
</template>
<script>
export default {
  name: 'comp-header',
  props: {
    titleHeader: String,
    },
  data() {
    return {
      text: 'Header component'
    }
  },
  methods: {
    changeTitleHeader(e) {
      // ko dc thay doi truc tiep props tu comp child
      // truyen sk len comp parent
      var data = {
        title: 'test -> data truyen thong qua event'
      }
      this.$emit('changeTitleEvent', data)
    },
  },
}

</script>
<style lang="">

</style>
