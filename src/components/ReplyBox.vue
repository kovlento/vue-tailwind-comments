<template>
  <div class="pl-8 border-l-2 border-gray-200">
    <slot />
  </div>
  <button class="pt-4 pb-10 text-blue-600">回复</button>
</template>
<script lang="ts">
import{ defineComponent }from 'vue';
export default defineComponent({
  name: "",
  setup: () => {

  }
})
</script>
<style lang="scss" scoped>

</style>