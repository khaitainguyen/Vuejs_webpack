<template lang="">
  <div class="list-user">
    <p>  List user components </p>
    <user
      v-for="user in listUserDetail"
      v-bind:key="user.id"
      v-bind:user="user"
      v-on:deleteUser="deleteUser"
    />
    <!-- <user />
    <user />
    <user /> -->
  </div>
</template>
<script>
import User from './User.vue';
export default {
  name: 'list-user',
  props: {
    listUserDetail: {
      type: Array,
      default: [],
    }
  },
  data() {
    return {
      listUser
    }
  },
  components: {
    User
  },
  methods: {
    deleteUser(data) {
      // console.log('delete user in list user', data);
      this.$emit('deleteUserEvent', data);
    }
  },
}
</script>
<style>
  .list-user {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }
  .list-user .user {
    padding: 30px;
    margin-bottom: 30px;
    border: 1px solid #333;
    width: calc(33.33% - 20px);
  }
</style>
