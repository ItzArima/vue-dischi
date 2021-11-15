<template>
  <div class="disks-container" >
      <dischi  v-for="disco in dischi" :key="disco.author"/>
  </div>
</template>

<script>
import dischi from './dischi.vue'

export default {
    
    components: {
        dischi,
    }
}
</script>

<style>

</style>