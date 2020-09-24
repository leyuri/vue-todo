<template>
  <section>
    <ul>
      <li v-for="(Item, index) in propsdata" :key="Item" class="shadow">
        <i class="checkBtn fas fa-check" aria-hidden="true"></i>
        {{ Item }}
        <span class="removeBtn" type="button" @click="removeItem(Item, index)">
          <i class="far fa-trash-alt" aria-hidden="true"></i>
        </span>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  props: ['propsdata'],
  methods: {
    removeItem(Item, index) {
      this.$emit('removeTodo', Item, index);
      // 이벤트를 발생시키고 app 컴포넌트로 전달, 
      // 선택한 할 일의 텍스트 (Iten)과 인덱스(Index)를 같이 보냄
      // 이벤트를 전달할 때 인자를 함께 전달할 수 있음 
    }
  }
}
</script>

<style scoped>
  ul {
    list-style-type: none;
    padding-left: 0px;
    margin-top: 0;
    text-align: left;
  }
  li {
    display: flex;
    min-height: 50px;
    height: 50px;
    line-height: 50px;
    margin: 0.5rem 0;
    padding: 0 0.9rem;
    background: white;
    border-radius: 5px;
  }
  .checkBtn {
    line-height: 45px;
    color: #62acde;
    margin-right: 5px;
  }
  .removeBtn {
    margin-left: auto;
    color: #de4343;
  }

</style>
