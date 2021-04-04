<template>
<v-app>
  <!-- <v-content> -->
  <v-card
    color="grey lighten-4"
    flat
    height="auto"
    tile
  >
    <v-toolbar dark dense color="orange">
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>NUXTER</v-toolbar-title>

      <v-spacer></v-spacer>

    <v-toolbar-items>
      <v-btn
      
      elevation = "12"
      color='orange'
      rounded>
        <NLink to="/"> Home </NLink>
      </v-btn>
      <v-btn
      elevation="12"
      color="orange"
      rounded>
        <nuxt-link to="/weather-app"> Weather APP </nuxt-link>
      </v-btn>
      <!-- <v-btn >
        <NLink to="/about"> About </NLink>
      </v-btn>
      <v-btn>
        <NLink to="/inspire"> Inspire </NLink>
      </v-btn> -->
    </v-toolbar-items>
    </v-toolbar>
  </v-card>
    <v-main>
    <nuxt/>
    </v-main>
  
  
</v-app>
  
</template>

<script>
export default {

}
</script>

<style>

a{
  text-decoration: none;
}
a:hover{
  color: white;
}


</style>