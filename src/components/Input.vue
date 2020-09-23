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
            if (this.newItem !== "") { //input box의 입력값이 있을 때만 저장
                var value = this.newItem && this.newItem.trim(); //앞뒤 공백 문자열 제거
                localStorage.setItem(value, value);
                this.clearInput();
            }
            
        },
        clearInput() { //inputbox의 입력값 조기화
            this.newItem = '';
        }
    }
}
</script>

<style>
</style>
