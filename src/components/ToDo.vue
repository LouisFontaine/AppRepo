<template>
  <v-container>
      <div class="formulaire">
      <p>Add a new To Do tasks </p>
      <input style={border-color:white} v-model="name" placeholder="Name" />
      <textarea v-model="desc" placeholder="Description" />
      <button v-on:click="addToDo(name, desc)">Add</button>
      </div>
    <v-list v-for="todo in todos" v-bind:key="todo.id">
        <p>Activity : {{ todo.title }}</p>
        <div class='meta'>
          {{ todo.description }}
        </div>
        <br />
        <button v-on:click="delToDo(todo.id)">Delete</button>
    </v-list>
  </v-container>
</template>

<script>
export default {
  props: ['todos'],
  methods: {
    addToDo (name, desc) {
      this.todos.push({
        title: name,
        description: desc,
        id: this.todos.length + 1 })
    },
    delToDo (identifiant) {
      var i = 0
      for (i = 0; i < this.todos.length; i++) {
        if (this.todos[i].id === identifiant) {
          this.todos.splice(i, 1)
        }
      }
    }
  }
}

</script>

<style>
.formulaire{
    background-color:blue;
}
p{
    color: black;
    font-size: 1cm;
    text-align: center;
}
</style>
