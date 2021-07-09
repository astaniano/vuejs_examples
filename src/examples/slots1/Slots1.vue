<template>
	<UserList :users="users" />
</template>

<script>
import UserList from "./components/UserList.vue";

import { loadUsers } from "./api.js";
export default {
	name: "Slots1",
	components: {
		UserList,
	},
	data() {
		return { users: [] };
	},

	mounted() {
		loadUsers().then((users) => {
			this.users = users;
		});
	},
};
</script>
