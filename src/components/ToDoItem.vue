<template>
  <div class="my-3" v-bind:class="{ strike: item.done }">
    <h5>{{ item.title }}</h5>
    <p class="mb-0">{{ item.description }}</p>
    <div class="form-group form-check">
      <input
        type="checkbox"
        class="form-check-input"
        v-on:change="toggleDone"
        v-bind:checked="item.done"
      />
      <label class="form-check-label">Done</label>
    </div>
    <button class="btn btn-danger" v-on:click="deleteItem">Delete</button>
  </div>
</template>

<script>
export default {
  props: ["item"],
  methods: {
    deleteItem() {
      this.$emit("delete-item", this.item);
    },
    toggleDone() {
      this.$emit("toggle-done", this.item);
    },
  },
};
</script>

<style>
.strike {
  text-decoration: line-through;
}
</style>
