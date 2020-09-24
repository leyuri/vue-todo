<template>
  <section>
    <ul>
      <li v-for="(Item, index) in Items" :key="Item" class="shadow">
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
  data() {
    return {
      Items: []
    }
  },
  methods: {
    removeItem(Item, index) {
      console.log(Item, index);
    }
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
