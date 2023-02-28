<template>
  <Suspense>
      <template #default>
        <user />
      </template>
      <template #fallback>
        <p>Loading data...</p>
      </template>
    </Suspense>
</template>

<script setup>
import user from '../components/UserComponent.vue'


</script>

<style lang="scss" scoped>

</style>