<template>
  <div>
    <List
    :items="users"
    :fields="['username', 'name']"
    :itemComponent="$options.listItemComponents.User"
  />
  <List
    :items="todos"
    :fields="['title']"
    :itemComponent="$options.listItemComponents.Todo"
  />
  </div>
</template>

<script>
import List from "./components/List.vue";
import User from "./components/User.vue";
import Todo from "./components/Todo.vue";

import { loadUsers, loadTodos } from "./api.js";
export default {
  name: "Slots1",
  components: {
    List,
  },
  listItemComponents: {
    User,
    Todo,
  },
  data() {
    return { users: [], todos: [] };
  },
  mounted() {
    loadUsers().then((users) => {
      this.users = users;
    });
    loadTodos().then((todos) => {
      this.todos = todos;
    });
  },
};
</script>
