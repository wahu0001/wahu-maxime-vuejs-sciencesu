<template>
  <div class="media mb-2">
    <img
      class="mr-3 rounded"
      style="height: 120px"
      :src="employee.avatar"
      alt="Generic placeholder image"
    />
    <div class="media-body">
      <h5 class="mt-0">{{ employee.firstName }} & {{ employee.lastName }}</h5>
      <span class="badge badge-info">{{ employee.email }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Employee",
  props:{
      employee: Object,
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
