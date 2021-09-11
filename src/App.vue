<template>
  <div id="app">
      <div class="container">
        <button v-on:click="title = 'Event up in vue'">Change title from Component App.vue</button>
        <!-- <ComponentHeader></ComponentHeader>
        <ComponentHeader /> -->
        <component-header
          v-bind:titleHeader="title"
          v-on:changeTitleEvent="handleChangeTitle"
        />
        <img src="./assets/logo.png">
        <h1>{{ msg }}</h1>
        <list-user
          v-bind:listUserDetail="listUserDetail"
          v-on:deleteUserEvent="deleteUserEvent"
        />
        <component-footer />
        <demo-ref />
        <demo-slot>
          <div class="app-slot">
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Aliquid porro praesentium ad asperiores debitis optio voluptates, assumenda voluptatum at nobis quo dolorum deserunt ipsa, temporibus possimus rerum nesciunt qui aspernatur?</p>
          </div>
        </demo-slot>
      </div>
  </div>
</template>

<script>
/**
App
  CompHeader
  ListUser
  CompFooter

 */
import ComponentHeader from './components/ComponentHeader.vue';
import ComponentFooter from './components/CompFooter.vue';
import ListUser from './components/ListUser.vue';
import DemoRef from './components/DemoRef.vue';
import DemoSlot from './components/DemoSlot.vue';
export default {
  name: 'app',
  data () {
    return {
      msg: 'Webpack vuejs admin',
      title: 'Title props',
      listUserDetail: [
        { id: 100, email: 'test@gmail.com', active: true},
        { id: 101, email: 'test2@gmail.com', active: false},
        { id: 102, email: 'test3@gmail.com', active: true},
        { id: 103, email: 'test4@gmail.com', active: false},
        { id: 104, email: 'test5@gmail.com', active: true},
      ]
    }
  },
  components: {
    ComponentHeader,
    ComponentFooter,
    ListUser,
    DemoRef,
    DemoSlot
  },
  methods: {
    handleChangeTitle( data) {
      // this.title = 'Lap trinh Vuejs -> Header changed'
      this.title = data.title;
      console.log('handleChangeTitle App.vue')
    },
    deleteUserEvent(data) {
      var indexDelete = -1;
      this.listUserDetail.forEach((u, idx) => {
        if(u.id == data.id){
          indexDelete = idx;
        }
      });
      if(indexDelete != -1) {
        this.listUserDetail.splice(indexDelete, 1);
      }
      // console.log('indexDlelte sau khi chay la', indexDelete);
      // console.log('delete user event in App.vue', data);
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  max-width: 1170px;
  margin: 0 auto;
  padding: 0 15px;
  min-height: 3000px;
}
</style>
