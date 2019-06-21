<template>
  <div>
    <form v-on:submit="addTodo">
      <div class="row mb-3 mr-0">
        <div class="col-9">
          <input
            type="text"
            name="title"
            class="form-control"
            v-model="title"
            placeholder="Enter your text.."
          >
        </div>

        <div class="col-3">
          <input type="submit" value="Submit" class="btn btn-block btn-dark">
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "AddToDo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false
      };
      this.$emit("add-todo", newTodo);
      this.title = "";
    }
  }
};
</script>

<style scoped>
</style>
