<template>
  <div class="background d-flex gap-vertical">
    <h2>OpenFinances</h2>
    <div class="row-container justify-center">
      <default-button @click="showModal(true)"></default-button>
    </div>
    <div class="row-container justify-space-between">
      <default-card></default-card>
      <default-card></default-card>
      <default-card></default-card>
    </div>
    <default-table class="teste"></default-table>
    <add-finance-modal v-if="isModalOpen" @close="showModal(false)"></add-finance-modal>
  </div>
</template>

<script>
  import DefaultTable from "./components/DefaultTable.vue";
  import DefaultCard from "../src/components/DefaultCard.vue";
  import DefaultButton from "../src/components/DefaultButton.vue";
  import AddFinanceModal from "../src/components/AddFinanceModal.vue";

  export default {
    name: 'App',
    data() {
      return {
        isModalOpen: false
      };
    },
    components: {
      DefaultTable,
      DefaultCard,
      DefaultButton,
      AddFinanceModal
    },
    methods: {
      showModal(show) {
        var body = document.querySelector('body');
        if (show === true) {
          this.isModalOpen = true;
          body.style.overflow = "hidden";
        } else if (show === false){
          this.isModalOpen = false;
          body.style.overflow = "auto";
        }
      }
    }
  };
</script>

<style>
  #app {
    display: flex;
    flex-direction: column;
    align-items: center;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    padding: 50px 0;
  }
</style>
