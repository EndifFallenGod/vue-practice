<template>
  <form class="form" @submit.prevent="onSubmit">
    <input type="text" v-model="title" />
    <button type="submit">Create</button>
  </form>
</template>
<script>
export default {
  name: "ToDoForm",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    onSubmit() {
      const newItem = {
        id: Date.now(),
        title: this.title,
        completed: false,
      };
      this.$emit("createItem", newItem);
      this.title = "";
    },
  },
};
</script>
<style>

</style>