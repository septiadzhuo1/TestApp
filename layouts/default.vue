<template>
  <div>
    <v-toolbar dense>
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
          <v-toolbar-title><nuxt-link to="/">Home</nuxt-link></v-toolbar-title>
        <v-spacer></v-spacer>
  
        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>
      </v-toolbar>
      <nuxt/>
  </div>
</template>

<style>
a {
  color: inherit; /* blue colors for links too */
  text-decoration: inherit; /* no underline */
}
</style>
