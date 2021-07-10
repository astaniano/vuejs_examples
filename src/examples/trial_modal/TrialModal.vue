<template>
  <div>
    <div>
      ddddddddddddddddd before
      <button @click="openModal">open modal</button>
    </div>
    <div v-if="isModalOpen">
      <MyModal @close="onModalClosed">
        <template #center>
          center content JOOOOOO
        </template>
        <template #bottom>
          <input
            type="text"
            v-model="modalCloseWord"
            @keyup="isModalReadyToClose"
          />
          <button @click="closeModal" :disabled="isOkBtnDisabled">okey</button>
        </template>
      </MyModal>
    </div>
    <div>
      dddddddddddddd after
    </div>
  </div>
</template>

<script>
import MyModal from "./MyModal.vue";
export default {
  name: "TrialModal",
  components: {
    MyModal,
  },
  data() {
    return {
      isModalOpen: false,
      modalCloseWord: "",
      isOkBtnDisabled: true,
      isOkBtnClicked: false,
    };
  },
  mounted() {},
  methods: {
    openModal() {
      this.isModalOpen = true;
    },
    closeModal() {
      this.isOkBtnClicked = true;
      this.isModalOpen = false;
      this.modalCloseWord = "";
      this.isOkBtnDisabled = true;
    },
    isModalReadyToClose() {
      if (this.modalCloseWord.toLowerCase() === "bb") {
        this.isOkBtnDisabled = false;
      } else {
        this.isOkBtnDisabled = true;
      }
    },
    onModalClosed() {
      console.log("modal was closed");
    },
  },
};
</script>
