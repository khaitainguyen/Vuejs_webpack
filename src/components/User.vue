<template lang="">
  <div class="user">
    <p> {{ user.email}} </p>
    <button
      v-on:click="handleDelete"
      class="delete">Delete</button>
  </div>
</template>
<script>
export default {
  name: 'user',
  props: {
    user: {
      type: Array,
      default: null
    }
  },
  data() {
    return {

    }
  },
  methods: {
    handleDelete(e) {
      var data = {
        id: this.user.id
      }
      // console.log('handleDelete');
      this.$emit('deleteUser', data);
    }
  },
}
</script>
<style lang="">
  .user {
    position: relative;
  }
  .user .delete  {
    position: absolute;
    top: 0;
    right: 0;
  }
</style>
