<script>
  import { store } from './store';
  import HeaderApp from './components/HeaderApp.vue';
  import MainApp from './components/MainApp.vue';

  export default {
    data() {
      return {
        store,
      };
    },
  };
</script>
<template>
  <HeaderApp/>
  <MainApp/>
</template>
<!-- <style></style> -->
