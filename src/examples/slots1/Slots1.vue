<template>
  <div>
    <List :items="users" :fields="['username', 'name']">
      <template #item="{ item: user }">
        {{ user.name }} ({{ user.username }})
      </template>
    </List>
    <List :items="todos" :fields="['title']">
      <template #item="slotProps">
        <Todo :item="slotProps.item" />
      </template>
    </List>
  </div>
</template>

<script>
import List from "./components/List.vue";
// import User from "./components/User.vue";
import Todo from "./components/Todo.vue";

import { loadUsers, loadTodos } from "./api.js";
export default {
  name: "Slots1",
  components: {
    List,
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
