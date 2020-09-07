<template>
  <div class="home">
    <div v-if="!isMobile()">
      <h1>desktop-home</h1>
    </div>
    <div v-else>
      <MobileHome />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {
    MobileHome: () =>
      import(/* webpackChunkName: "mobile-home" */ "./mobile/MobileHome.vue"),
  },
  methods: {
    isMobile() {
      if (screen.width <= 760) {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>
