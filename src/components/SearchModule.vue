<template>
  <div class="search">
    <h3>Поиск</h3>
    <input type="text" v-model="text" @input="emitText" />
    {{ text }}
  </div>
</template>

<script>
export default {
  name: "SearchModule",
  data() {
    return {
      text: "",
    };
  },
  methods: {
    emitText() {
      this.$emit("getText", this.text);
    },
  },
};
</script>

<style>
.search {
  margin: 10px;
}
</style>
