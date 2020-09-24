<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newItem" placeholder="Type what you have to do" 
    v-on:keypress.enter="addTodo">
    <span class="addContainer" v-on:click="addTodo">
      <i class="addBtn fas fa-plus" aria-hidden="true"></i>
    </span>
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

<style scoped>
input:focus {
  outline: none;
}
.inputBox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}
.inputBox input {
  border-style: none;
  font-size: 0.9rem;
}
.addContainer {
  float: right;
  background: #fccbcb;
  display: inline-block;
  width: 3rem;
  border-radius: 0 5px 5px 0;
}
.addBtn {
  color: white;
  vertical-align: middle;
}
</style>
