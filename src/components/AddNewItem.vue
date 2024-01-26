<template>
  <div class="my-3">
    <h4>Add a to-do</h4>
    <form v-on:submit.prevent="addItem">
      <div class="mb-3">
        <label for="title" class="form-label">Add Title</label>
        <input class="form-control" id="title" name="title" v-model="title" />
      </div>
      <div class="mb-3">
        <label for="description" class="form-label">Add Description</label>
        <input
          class="form-control"
          id="description"
          name="description"
          v-model="description"
        />
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: null,
      description: null,
    };
  },
  methods: {
    addItem() {
      const newItem = {
        title: this.title,
        description: this.description,
        done: false,
      };
      this.$emit("add-item", newItem);
    },
  },
};
</script>
