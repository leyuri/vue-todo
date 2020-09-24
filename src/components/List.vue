<template>
  <section>
    <ul>
      <li v-for="Item in Items">{{ Item}}</li>
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
</style>
