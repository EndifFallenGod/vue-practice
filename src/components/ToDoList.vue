<template>
  <div class="list">
    <ul>
      <to-do-item
        v-for="(item, index) in list"
        :key="index"
        :item="item"
        @deleteItem="deleteItem"
      />
    </ul>
  </div>
</template>

<script>
import ToDoItem from "./ToDoItem";
export default {
  name: "ToDoList",
  components: { ToDoItem },
  props: {
    list: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {};
  },
  methods: {
    deleteItem(id) {
      this.$emit("deleteItem", id);
    },
  },
};
</script>
<style>
.list {
  max-width: 500px;
}
</style>
