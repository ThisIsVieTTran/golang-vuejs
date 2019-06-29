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
            Hamburger Menu
          </v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-toolbar>

    <v-divider></v-divider>

    <v-list two-line class="pt-0">
      <v-list-tile v-for="item in items" :key="item.title" exact="item.link" router :to="item.link">
        <v-list-tile>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-tile>

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
          icon: 'home',
          link: 'home'
        },
        {
          title: 'Directions',
          icon: 'directions',
          link: 'directions'
        },
        {
          title: 'About',
          icon: 'question_answer',
          link: 'about'
        }
      ],
      right: null
    }
  }
}
</script>
