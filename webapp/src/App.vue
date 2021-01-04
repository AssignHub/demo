<template>
  <v-app>
    <v-app-bar
      app
      color="white darken-2"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="@/assets/logo.png"
          transition="scale-transition"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-avatar>
        <img src="@/assets/jim.jpg">
      </v-avatar>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<style>
html {
  overflow-y: auto !important;
}
</style>

<script>
export default {
  name: 'App',
};
</script>
