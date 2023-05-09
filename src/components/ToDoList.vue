<template>
  <div class="container">
      <h1 class="text-center">To do List</h1>
      <div>
          <input type="text" v-model="todo" placeholder="Nouvelle tâche" />
          <button class="btn-add" @click="addTodo">Ajouter une tâche</button>
      </div>
      <table class="table table-bordered">
          <thead>
              <tr>
                  <th scope="col">Tâche</th>
                  <th scope="col">Date</th>
                  <th scope="col"></th>
                  <th scope="col"></th>
              </tr>
          </thead>
          <tbody>
              <tr v-for="(todo, index) in todos" :key="index">
                  <td scope="row">{{todo.name}}</td>
                  <td scope="row">{{todo.date}}</td>
                  <td>
                      <button class="del-btn" @click="deleteTodo(index)">Supprimer</button>
                  </td>
                  <td>
                      <button class="edit-btn" @click="editTodo(index)">Modifier</button>
                  </td>
              </tr>
  
          </tbody>
      </table>
  
  </div>
  </template>
  
  <script>
  export default {
      name: "TodoApp",
      props: {
          msg: String,
      },
      data() {
          return {
              task: "",
              editTodo: null,
              todos: []
          }
        },
        methods: {
          deleteTodo(index) {
            this.todos.splice(index, 1)
          },
          editTodo(index) {
            this.todo = this.todos[index].name,
            this.editTodo = index
          },
          addTodo() {
            if (this.todo.length === 0) {
              return;
            }
            if (this.editTodo != null) {
              this.todos[this.editTodo].name = this.task;
              this.editTodo = null
              
            } else {
              this.todos.push({
                name: this.todo,
                date: new Date().toLocaleDateString("fr-FR", {
                  year: "numeric",
                  month: "long",
                  day: "numeric",
                }),
              });  
            }
          }
  
      }
  
  }
  </script>
  
  <style scoped>
  </style>