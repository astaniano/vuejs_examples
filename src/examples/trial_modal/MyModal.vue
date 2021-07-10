<template>
  <div>
    <div>heading of the modal will be here</div>
    <slot name="center">default content for center slot</slot>
    <slot name="bottom">default content for bottom slot</slot>
  </div>
</template>

<script>
export default {
  name: "MyModal",
  props: {},
  components: {},
  data() {
    return {};
  },
  mounted() {},
  beforeDestroy() {
    this.$emit("close");
  },
  methods: {},
  watch: {},
};
</script>
