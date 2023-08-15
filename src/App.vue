<template>
  <div id="app">
    <search-module />
    <to-do-form @createItem="createItem" />
    <to-do-list :list="list" @deleteItem="deleteItem" />
  </div>
</template>

<script>
import ToDoForm from "./components/ToDoForm";
import ToDoList from "./components/ToDoList";
import SearchModule from "./components/SearchModule";

export default {
  name: "App",
  components: { ToDoForm, ToDoList, SearchModule },
  data() {
    return {
      list: [
        { id: 1, title: "Hello", completed: false },
        { id: 2, title: "ffdfdf", completed: false },
        { id: 3, title: "123hthrth", completed: false },
      ],
    };
  },
  methods: {
    createItem(item) {
      this.list.push(item);
    },
    deleteItem(id) {
      this.list = this.list.filter((t) => t.id !== id);
    },
  },
};
</script>
