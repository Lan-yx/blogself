<template>
  <div class="nav">
    <Header></Header>
  </div>
  
  <router-view />
</template>

<script>
  import Header from "@/components/Header.vue";

  export default{
    name: "out",
    components: {
      Header
    }
  }
</script>

<style>

</style>
