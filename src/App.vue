<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>TP 1 : </span>
        <span class="font-weight-light">My Project</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        text
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank">
      </v-btn>
    </v-app-bar>

    <v-content>
      <ToDo/>
    </v-content>
  </v-app>
</template>

<script>
import ToDo from './components/ToDo'

export default {
  name: 'App',
  components: {
    ToDo
  },
  data: () => ({
    //
  })
}
</script>
