<template>
  <v-container fill-height>
    <v-layout justify-center align-center>
      <h1>{{ todo.title }}</h1>
      <p>{{ todo.completed ? 'Completed' : 'Processing' }}</p>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  async asyncData ({ $axios, params }) {
    const  todo  = await $axios.$get('https://jsonplaceholder.typicode.com/todos/1');

    return { todo };
  }
}
</script>