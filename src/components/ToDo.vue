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
            </v-col>

            <v-col cols="12" md="4">
              <ol>
                  <li>
                    {{todoList}}
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
    todoList: []
  }),
  methods: {
    addTodo () {
      this.todoList.push({
        title: this.title,
        content: this.content
      })
      console.log(JSON.stringify(this.todoList))
    }
  }
}
</script>
