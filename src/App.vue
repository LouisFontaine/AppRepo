<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vuetify</span>
        <span class="font-weight-light">MATERIAL DESIGN</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        flat
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
      </v-btn>
    </v-toolbar>

    <v-content>
      <ToDo v-bind:todos="todos"></ToDo>
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
  data () {
    return {
      todos: [{
        title: 'Do some homeworks',
        description: 'Code the Todo App in Vue.Js',
        id: 0
      }, {
        title: 'Clean the car',
        description: 'Clean and repair the Opel Corsa',
        id: 1
      }, {
        title: 'Buys some food',
        description: 'Buy some pasta and some sauce',
        id: 2
      }]
    }
  }
}

</script>
