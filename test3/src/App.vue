<template>
  <v-app>
    <Navbar></Navbar>
    <v-content class="mx-10 my-5">
      <router-view></router-view>
    </v-content>
    
  </v-app>
</template>

<script>
import Navbar from '@/components/Navbar.vue'
export default {
  components :{
    Navbar
  },

  data: () => ({
    //
  }),
};
</script>
