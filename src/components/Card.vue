<template>
  <v-card
    class="ma-md-4 mx-lg-auto"
    max-width="400"
    @click.middle="newTabPressEvent(title.siteURL)"
    @click.native="pressEvent(title.siteURL)">
    <v-img
      class="white--text align-end"
      height="200px"
      :src="getImgUrl(title.Image)">
      <v-card-title>{{title.Name}}</v-card-title>
    </v-img>
  </v-card>
</template>

<script>
 export default {
    props:['title'],
    methods: {
        pressEvent : function (url) {
          window.location.href = url
        },
        newTabPressEvent : function (url) {
          window.open(url, '_blank');
        },
        getImgUrl(pic) {
          return require('../Images/'+pic)
        }
    },
 }
</script>