<template>
    <div>
        <input type="text" v-model="newItem">
        <button>ADD</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newItem: ''
        }
    }
}
</script>

<style>
</style>
