<template>
  <div
    class="container mx-auto flex grid grid-flow-col grid-cols-3 grid-rows-2 gap-4"
  >
    <div class="mx-auto flex"><ServiceCard /></div>
    <div class="mx-auto flex"><ServiceCard /></div>
    <div class="mx-auto flex"><ServiceCard /></div>
    <div class="mx-auto flex"><ServiceCard /></div>
    <div class="mx-auto flex"><ServiceCard /></div>
    <div class="mx-auto flex"><ServiceCard /></div>
  </div>
</template>

<script>
import ServiceCard from '@/components/ServiceCard.vue'
export default {
  components: { ServiceCard },
}
</script>
