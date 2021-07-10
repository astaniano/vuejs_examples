<template>
  <div>
    <button @click="managePopup">Открыть окно</button>
    <Popup ref="confirmationPopup">
      Вы действительно хотите освоить правильные подходы к проектированию систем
      во Vue?
      <template #actions="{ confirm }">
        Напишите
        <input
          :placeholder="$options.CONFIRMATION_TEXT"
          v-model="confirmation"
        />
        &nbsp;
        <button @click="confirm" :disabled="!isConfirmationCorrect">OK</button>
      </template>
    </Popup>
  </div>
</template>

<script>
import Popup from "./Popup.vue";
export default {
  components: { Popup },
  data() {
    return { confirmation: "" };
  },

  CONFIRMATION_TEXT: "confirm",

  computed: {
    isConfirmationCorrect() {
      return this.confirmation === this.$options.CONFIRMATION_TEXT;
    },
  },

  methods: {
    async managePopup() {
        this.confirmation = "";
        
        const confirmed = await this.$refs.confirmationPopup.open();
        if (confirmed) {
            alert("confirmed");
        }
    },
  },
};
</script>
