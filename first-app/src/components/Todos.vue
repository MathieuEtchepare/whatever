<template>
    <v-container>
        <v-form>
          <v-text-field
          v-model="name"
          placeholder="Enter a new Todo"
          label="Title of your To do"
          ></v-text-field> <br/>
          <v-textarea
          v-model="description"
          label="Enter a description"
          placeholder="add multiple lines"></v-textarea>
          <v-btn
          color="success"
          @click="addTodo"
          >Add Todo</v-btn>
        </v-form>
          <v-list>
            <v-list-tile
            v-bind:key="i"
            v-for="(todo,i) in todos">
            <v-list-tile-title>
              {{ todo.name }}
            </v-list-tile-title>
            <v-list-tile-content>
              {{ todo.desc }}
            </v-list-tile-content>
              <v-btn v-on:click="deleteTodo(i)">X</v-btn>
            </v-list-tile>
        </v-list>
    </v-container>
</template>
<script>
export default {
  data: () => ({
    todos: []
  }),
  methods: {
    addTodo: function () {
      this.todos.push({ name: this.name, desc: this.description })
    },
    deleteTodo (i) {
      this.todos.splice(i, 1)
    }
  }
}
</script>
