<template>
<nav>


  <v-toolbar app>
    <v-toolbar-side-icon @click="drawerVis = !drawerVis"></v-toolbar-side-icon>
    <v-toolbar-title>SomeApp</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
      <v-btn flat>Descriptive</v-btn>
      <v-btn flat>Predictive</v-btn>
      <v-btn flat>Prescriptive</v-btn>
    </v-toolbar-items>
  </v-toolbar>

  <v-navigation-drawer v-model="drawerVis" app>
    <v-toolbar flat>
      <v-list>
        <v-list-tile>
          <v-list-tile-title class="title">
            Application
          </v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-toolbar>

    <v-divider></v-divider>

    <v-list dense class="pt-0">
      <v-list-tile v-for="item in items" :key="item.title">
        <v-list-tile-action>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-tile-action>

        <v-list-tile-content>
          <v-list-tile-title>{{ item.title }}</v-list-tile-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list>
  </v-navigation-drawer>

</nav>
</template>
<script>
export default {
  data() {
    return {
      drawerVis: false,
      items: [{
          title: 'Home',
          icon: 'dashboard'
        },
        {
          title: 'About',
          icon: 'question_answer'
        }
      ],
      right: null
    }
  }
}
</script>
