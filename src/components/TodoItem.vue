<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <div class="form-group">
      <input type="checkbox" v-on:change="markComplete">
      {{todo.title}}
      <button v-on:click="$emit('del-todo',todo.id)" class="del">x</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}

.is-complete {
  color: green;
  font-weight: bold;
}

.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 8px 15px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>
