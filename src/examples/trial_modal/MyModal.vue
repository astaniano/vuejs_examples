<template>
  <div v-if="isOpen">
    <div>heading of the moal will be here</div>
    <slot name="center">default content for center slot</slot>
    <slot name="bottom">default content for bottom slot</slot>
  </div>
</template>

<script>
export default {
  name: "MyModal",
  props: {
    isOpen: { type: Boolean, required: true },
    isOkClicked: { type: Boolean, required: true },
  },
  components: {},
  data() {
    return {};
  },
  mounted() {},
  methods: {
    afterOkBtnClick() {
      console.log("yes!!!")
    },
  },
};
</script>
