<template>
  <div>
    <button @click="openPopup">Открыть окно</button>
    <Popup
      :is-open="isPopupOpen"
      @ok="popupConfirmed"
      @close="isPopupOpen = false"
    >
      Вы действительно хотите освоить правильные подходы к проектированию систем
      во Vue?
    </Popup>
  </div>
</template>

<script>
import Popup from "./Popup.vue";
export default {
  components: { Popup },
  data() {
    return { isPopupOpen: false };
  },

  computed: {},

  methods: {
    openPopup() {
      this.confirmation = "";
      this.isPopupOpen = true;
    },

    popupConfirmed() {
      alert("Confirmed!");
      //   this.isPopupOpen = false;
    },
  },
};
</script>
