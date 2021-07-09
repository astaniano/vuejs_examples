<template>
  <div>{{ item.name }} ({{ item.username }})</div>
</template>

<script>
export default {
  props: {
    item: { type: Object, required: true },
  },
};
</script>
