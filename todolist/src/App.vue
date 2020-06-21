<template>
  <div id="app">
    <input v-model="inputValue" placeholder="todo" />
    <button @click="addTask">提交</button>
    <ul>
      <todoItem
        v-for="(item, index) in taskList"
        :key="index"
        :item="item"
        :index="index"
        @deltask="delTask"
      ></todoItem>
    </ul>
  </div>
</template>

<script>
import todoItem from "./components/todoItem.vue";

export default {
  name: "App",
  components: {
    todoItem,
  },
  data: function() {
    return { inputValue: "", taskList: [] };
  },
  methods: {
    addTask: function() {
      this.taskList.push(this.inputValue);
      this.inputValue = "";
    },
    delTask: function(index) {
      this.taskList.splice(index, 1);
    },
  },
};
</script>

<style></style>
