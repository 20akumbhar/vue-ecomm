<template>
  <div class="categories">
    <div v-for="icon in icons" v-bind:key="icon.icon" class="category">
      <font-awesome-icon :icon='[icon.type, icon.icon]' />
    </div>
  </div>
</template>

<script>
export default {
    data: function(){
        return{
            icons: [{type:'fas',icon:'user-tie'},{type:'fab',icon:'cotton-bureau'}]
        };
    }
};
</script>

<style>
</style>