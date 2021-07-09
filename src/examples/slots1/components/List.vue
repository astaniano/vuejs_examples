<template>
  <div>
    <input placeholder="filter..." v-model="filter" />
    <hr />
    <ul>
      <li v-for="item in filteredItems" :key="item.id">
        <component :is="itemComponent" :item="item" />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    items: { type: Array, required: true },
    fields: { type: Array, required: true },
    itemComponent: { type: Object, required: true },
  },
  data() {
    return { filter: "" };
  },
  computed: {
    filteredItems() {
      return this.filter
        ? this.items.filter((item) =>
            this.fields.some((field) =>
              item[field].toLowerCase().includes(this.filter.toLowerCase())
            )
          )
        : this.items;
    },
  },
};
</script>
