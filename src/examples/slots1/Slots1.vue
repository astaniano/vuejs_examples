<template>
  <List
    :items="users"
    :fields="['username', 'name']"
    :itemComponent="$options.listItemComponents.User"
  />
</template>

<script>
import List from "./components/List.vue";
import User from "./components/User.vue";

import { loadUsers, loadTodos } from "./api.js";
export default {
  name: "Slots1",
  components: {
    List,
  },
  listItemComponents: {
    User,
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
