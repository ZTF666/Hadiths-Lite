<template>
  <v-app dark >
    <v-app-bar app color="black" flat>
      <v-container class="py-0 fill-height">
        <v-avatar class="mr-10" color="grey darken-1" size="50">
          <img src="https://ztfportfolio.web.app/_nuxt/img/me.1fafa89.png" alt="">
        </v-avatar>
        <v-spacer></v-spacer>
        <v-btn  href="https://github.com/ZTF666/Al-Damiri-Hadiths-Lite"
        target="_blank"
        text >
         GitHub<v-icon>mdi-github</v-icon>
        </v-btn>
      </v-container>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt  />
      </v-container>
    </v-main>
  
   <v-footer app class="pa-3">
      <div>{{footer}}</div>
    <v-spacer></v-spacer>
    <div> &copy;2020</div>
  </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
   footer:"Made with 💜 by ZTF ",
  }
}}
</script>
