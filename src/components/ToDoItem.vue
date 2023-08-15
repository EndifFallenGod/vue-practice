<template>
  <li class="li">
    <span>
      {{ item.title }}
    </span>
    <button @click="deleteItem(item.id)" type="button">Delete</button>
  </li>
</template>

<script>
export default {
  name: "ToDoItem",
  data() {
    return {};
  },
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  methods: {
    deleteItem(id) {
      this.$emit("deleteItem", id);
    },
  },
};
</script>
<style>
.li {
  border: 1px solid #333;
  margin: 5px;
}
</style>
