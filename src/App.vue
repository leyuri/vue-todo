<template>
  <div id="app">
    <Header></Header>
    <Input></Input>
    <List></List>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from './components/Header';
import Input from './components/Input';
import List from './components/List';
import Footer from './components/Footer';



export default {
  components : {
    'Header' : Header,
    'Input' : Input,
    'List' : List,
    'Footer' : Footer,
  }
}
</script>

<style>
</style>
