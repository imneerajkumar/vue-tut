<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <div class="container my-3">
    <div class="jumbotron">
      <h1 class="display-4">About This Vue App</h1>
      <p class="lead">
        This is a simple to-do list, where you can add your task as well as
        delete it. You can mark your task as done. Lorem ipsum dolor, sit amet
        consectetur adipisicing elit. Modi velit deleniti numquam ipsa alias
        enim illo temporibus tempore similique, itaque molestias veniam eveniet?
        Libero temporibus quo illum eos repudiandae facilis?
      </p>
      <hr class="my-4" />
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eum numquam
        eius repellat deserunt labore, amet cum at. Aspernatur non in sed et
        dolore quidem ipsam, assumenda sunt atque ad aliquid.
      </p>
      <RouterLink class="btn btn-primary btn-lg" to="/">Try It</RouterLink>
    </div>
  </div>
</template>

<style></style>
