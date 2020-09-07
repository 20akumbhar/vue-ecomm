<template>
  <div class="nav">
    <nav id="nav">
      <div class="brand">Ecomm</div>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <font-awesome-icon v-on:click="changeOpen" v-if="!isSearchOpen" icon="search" />
      <font-awesome-icon v-on:click="changeOpen" v-else icon="times" />
    </nav>
    <div class="search" v-bind:class="{open : isSearchOpen}">
      <input type="search" placeholder="Search Here" />
      <font-awesome-icon icon="search" />
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data: function () {
    return {
      isSearchOpen: false
    };
  },
  methods:{
    changeOpen(){
      this.isSearchOpen=!this.isSearchOpen;
    }
  }
};
</script>

<style>
.nav nav {
  height: 50px;
  display: flex;
  background-color: #ff3a6b;
  align-items: center;
  color: #fff;
}
.nav nav .brand {
  margin: 20px;
  font-size: 1.4em;
}
.nav nav a {
  padding: 10px;
  text-decoration: none;
  color: #fff;
}
.nav nav svg {
  margin-left: auto;
  color: #fff;
  display: block;
  margin-right: 20px;
}
.nav .search {
  display: flex;
  align-items: center;
  overflow: hidden;
  max-height: 0px;
  transition: ease-in-out .4s;
}
.nav .search.open {
  border-bottom: 1px solid black;
  max-height: unset !important;
  transition: ease-in-out .4s;
}
.nav .search input {
  width: 90%;
  padding: 12px;
  font-size: 16px;
  border: none;
}
</style>