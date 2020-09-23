<template>
    <div>
        <input type="text" v-model="newItem">
        <button v-on:click="addTodo">ADD</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newItem: ''
        }
    },
    methods: {
        addTodo() {
            // console.log(this.newItem); //this.newItem의 this는 해당 컴포넌트를 가리킴
            localStorage.setItem(this.newItem, this.newItem);
        }
    }
}
</script>

<style>
</style>
