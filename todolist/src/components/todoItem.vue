<template>
  <li>{{ item }}&nbsp;<span class="del" @click="del">×</span></li>
</template>

<script>
export default {
  name: "todoItem",
  props: ["item", "index"],
  methods: {
    del: function() {
      this.$emit("deltask", this.index);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.del {
  color: red;
  cursor: pointer;
}
</style>
