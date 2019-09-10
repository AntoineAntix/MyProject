<template>
  <v-container>
    <v-layout text-center wrap>
      <v-form v-model="valid">
        <v-container>
          <v-row>

            <v-col cols="12" md="4">
              <v-text-field
                v-model="title"
                label="Title"
                required
              ></v-text-field>
            </v-col>

            <v-col cols="12" md="4">
              <v-text-field
                v-model="content"
                label="Content"
                required
              ></v-text-field>
            </v-col>

            <v-col cols="12" md="4">
              <v-btn v-on:click="addTodo">Add</v-btn>
              <v-btn v-on:click="seen">Del</v-btn>
            </v-col>

            <v-col cols="12" md="4">
              <ol>
                  <li v-for="(item, i) in todoList" :key="i">
                    {{ item.title }} : {{item.content}}
                    <v-btn v-if="seen_button" v-on:click="delTodo(i)">Del</v-btn>
                  </li>
              </ol>
            </v-col>

          </v-row>
        </v-container>
      </v-form>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    valid: false,
    title: '',
    content: '',
    seen_button: false,
    todoList: []
  }),
  methods: {
    addTodo () {
      this.todoList.push({
        title: this.title,
        content: this.content
      })
      console.log(JSON.stringify(this.todoList))
      this.seen_button = false
    },
    delTodo (i) {
      var x = window.confirm('Voulez vous suprimer cet élèment de la liste ?')
      if (x) {
        this.todoList.splice(i, 1)
        this.seen_button = false
      }
    },
    seen () {
      this.seen_button = true
    }
  }
}
</script>
