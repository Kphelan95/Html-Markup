<template>
  <v-app>
    <v-app-bar app color="primary" dark >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

       
      </div>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-content>
      <textbox v-on:changeBack="test($event)" />
      <display :html='this.html'/>
    </v-content> 
  </v-app>
</template>

<script>
//import HelloWorld from './components/HelloWorld';
import textbox from './components/TextBox';
import display from './components/DisplayHtml';

export default {
  name: 'App',

  components: {
    //HelloWorld,
    textbox,
    display
  },
  data : function () {
    return {
        html:""
    }
  },
 
   methods:{
     test : function(html){ //notes, pass this string into the display html compentent, then inside the compoint make it looks nice
        console.log(html); 
        this.html=html;
     }
  }
};
</script>

<style scoped>
.text-xs-right {
  white-space: nowrap;
}
</style>
