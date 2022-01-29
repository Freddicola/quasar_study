<template>
  <!-- q-page class="flex flex-center" -->
  <q-page class="flex">
    <div class="indices bg-green">
      Indices Region
    </div>
    <q-page-container>
      <!-- This is where pages get injected -->
      <router-view />
    </q-page-container>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageIndex'
})
</script>

<style lang="sass" scoped>
.indices
  width: 100%
  height: 250px

</style>
