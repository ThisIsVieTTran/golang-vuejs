<template>
<v-app>
  <toolbar></toolbar>
  <v-content>
    <router-view></router-view>
  </v-content>
</v-app>
</template>

<script>
// Make sure to add your components here!
import Toolbar from '@/components/Toolbar'
export default {
  name: 'App',
  components: {
    Toolbar
  },
  data() {
    return {
      //
    }
  }
}
</script>
