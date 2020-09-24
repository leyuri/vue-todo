<template>
  <div id="app">
    <Header></Header>
    <Input v-on:addTodo="addTodo"></Input>
    <List v-bind:propsdata="Items"></List>
    <Footer v-on:removeAll="clearAll"></Footer>
  </div>
</template>

<script>
import Header from './components/Header';
import Input from './components/Input';
import List from './components/List';
import Footer from './components/Footer';



export default {
  data() {
    return {
      Items: []
    }
  },
  methods : {
    clearAll() {
      localStorage.clear();
      this.Items = [];
    },
    addTodo(Item) {
      // 로컬 스토리지에 데이터를 추가하는 로직 
      localStorage.setItem(Item, Item);
      this.Items.push(Item);
    }
  },
  components : {
    'Header' : Header,
    'Input' : Input,
    'List' : List,
    'Footer' : Footer,
  },
  created() {
    if (localStorage.length > 0) {
      for (var i = 0; i < localStorage.length; i++) {
        this.Items.push(localStorage.key(i));
      }
    }
  }
}
</script>

<style>
body {
    text-align: center;
    background-color: #f6f6f6;
}

input {
    border-style: groove;
    width: 200px;
}

button {
  border-style: groove;
}

.shadow {
  box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.10);
}
</style>
