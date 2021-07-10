<template>
  <div v-if="isOpen" class="backdrop">
    <div class="popup">
      <h1>Внимание!</h1>
      <hr />
      <slot></slot>
      <hr />
      <div class="footer">
        <slot name="actions" :close="close">
          <button>Отмена</button>
          &nbsp;
          <button>Ok</button>
        </slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isOpen: {
      type: Boolean,
      required: true,
    },
  },
  methods: {
    // handleKeydown(e) {
    //   if (this.isOpen && e.key === "Escape") {
    //     this.close();
    //   }
    // },

    close() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.popup {
  top: 50px;
  padding: 20px;
  left: 50%;
  transform: translateX(-50%);
  position: fixed;
  z-index: 101;
  background-color: white;
  border-radius: 10px;
}

.popup h1 {
  text-align: center;
  margin: 0;
}

.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.8);
  z-index: 100;
}

.footer {
  text-align: right;
}
</style>
