<template>
  <v-app>
    <v-container fill-height>
      <v-row align="center"
        justify="center">
        <v-col v-for="site in sites" :key="site.id"
          cols="12"
          sm="3">
          <Card :title="site"/>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
  import Card from './components/Card';
  import sitesJson from './data/sites.json';

  export default {
    name: 'App',

    components: {
      Card
    },

    methods: {
      getBgImg() {
        return require('./Images/bg.jpg')
      }
    },

    data() {
      return {
        sites: sitesJson
      }
      
    }

  };
</script>

<style>
#app {
  background: url('./Images/bg.jpg')
    no-repeat center center fixed !important;
  background-size: cover;
}
</style>
