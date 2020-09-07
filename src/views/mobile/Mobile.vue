<template>
  <div class="mobile">
    <Navbar />
    <router-view />
  </div>
</template>

<script>
import Navbar from "@/components/mobile/Navbar.vue";
export default {
  components: {
    Navbar,
  },
};
</script>

<style>
</style>