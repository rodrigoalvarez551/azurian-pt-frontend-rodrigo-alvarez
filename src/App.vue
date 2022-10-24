<template>
  <div class="container mt-4">
    <tabla></tabla>
  </div>
</template>

<script>

import tabla from "@/components/tabla";
export default {
  name: 'App',
  components: {
    tabla
  }
}
</script>

<style>

.container {
  max-width: 1000px;
}
</style>
