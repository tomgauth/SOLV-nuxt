<template>
  <v-toolbar color="primary">
    <v-toolbar-side-icon>
      <div class="text-xs-center">
        <v-menu bottom left>
          <template v-slot:activator="{ on }">
            <v-btn
              dark
              icon
              v-on="on"
            >
              <v-icon>more_vert</v-icon>
            </v-btn>
          </template>

          <v-list>
            <v-list-tile
              v-for="(item, i) in items"
              :key="i"
              @click="item.link"
            >
              <v-list-tile-title>{{ item.title }}</v-list-tile-title>
            </v-list-tile>
          </v-list>
        </v-menu>
      </div>
    </v-toolbar-side-icon>
    <v-toolbar-title>
      <v-btn flat to="/">SOLV</v-btn>
    </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">

      <v-btn flat to="account/login" >Login</v-btn>
      <v-btn flat to="account/signup" >Signup</v-btn>
    </v-toolbar-items>
  </v-toolbar>
</template>

<script>
  import { mapState } from 'vuex'
  export default {
    data: () => ({
      items: [
        { title: 'Home', link: '/'},
        { title: 'Sentences', link: '/'}
      ]
    }),
  computed: mapState([
    'user'
  ])
  }
</script>

<style scoped>
.title {
  text-decoration: none !important;
}
.title:visited{
  color: white;
}
</style>
