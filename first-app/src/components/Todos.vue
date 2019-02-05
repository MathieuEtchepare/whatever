<template>
    <v-container>
        <v-form>
          <input v-model="name" placeholder="Enter a new Todo"> <br/>
          <textarea v-model="description" placeholder="add multiple lines"></textarea>
          <button v-on:click="addTodo">Add Todo</button>
        </v-form>
          <li v-for="(todo,i) in todos"
          :key="i"
          >
                {{ todo.name }} : {{ todo.desc }} <button v-on:click="deleteTodo(i)">X</button>
        </li>
    </v-container>
</template>
<script>
export default {
  data: () => ({
    todos: [ { name: 'Clean my room', desc: 'I really need to clean my room' } ]
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
