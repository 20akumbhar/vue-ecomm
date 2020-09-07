<template>
  <div id="app">
    <div v-if="!isMobile()">
      <Desktop />
    </div>
    <div v-else>
      <Mobile />
    </div>
  </div>
</template>
<script>
import Vue from 'vue'
import { library } from '@fortawesome/fontawesome-svg-core'
import { faSearch,faTimes,faUserTie } from '@fortawesome/free-solid-svg-icons'
import { faCottonBureau} from '@fortawesome/free-brands-svg-icons'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

library.add(faSearch)
library.add(faTimes)
library.add(faUserTie)
library.add(faCottonBureau)

Vue.component('font-awesome-icon', FontAwesomeIcon)
export default {
  components: {
    Mobile: () =>
      import(/* webpackChunkName: "mobile" */ "./views/mobile/Mobile.vue"),
    Desktop: () =>
      import(/* webpackChunkName: "desktop" */ "./views/desktop/Desktop.vue"),
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
<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
*:focus{
  outline: none;
  border: none;
}
</style>
