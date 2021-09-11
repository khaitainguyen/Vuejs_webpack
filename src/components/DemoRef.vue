<template lang="">
  <div class="demo-ref">
      <h3> Demo Ref</h3>
      <input
        type="file"
        ref="fileInputAvatar"
        style="display:none;"
      >
      <button
        class="avatar"
        v-on:click="handleClickInputAvatar"
      > Change avatar </button>
  </div>
</template>
<script>
export default {
  name: 'demo-ref',
  data() {
    return {

    }
  },
  methods: {
    handleClickInputAvatar(e) {
      this.$refs.fileInputAvatar.click()
    }
  },
}
</script>
<style lang="">
  .demo-ref {
    margin-top: 100px;
    padding: 100px 30px;
    border: 1px solid #000;
  }

  .avatar {
    color: #fff;
    border: 2px solid #333;
    padding: 12px 15px;
    background-color: #333;
    transition: all .3s ease;
    border-radius: 5px;
  }
  .avatar:hover {
    color: #333;
    background-color: #fff;
  }
</style>
