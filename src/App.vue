<template>
  <div class="background d-flex gap-vertical">
    <header class="row-container">
      <h2 class="logo"><span>u</span>Balance</h2>
    </header>
    <div class="row-container justify-end">
      <default-button @click="showModal(true)"></default-button>
    </div>
    <div class="row-container">
      <div class="column-container">
        <default-card></default-card>
        <default-card></default-card>
        <default-card></default-card>
      </div>
      <default-table :transactionsListProps="transactionsList"></default-table>
    </div>
    <add-finance-modal
      @save-movement="saveMovement"
      v-if="isModalOpen"
      @close="showModal(false)"
    ></add-finance-modal>
  </div>
</template>

<script>
import DefaultTable from "./components/DefaultTable.vue";
import DefaultCard from "../src/components/DefaultCard.vue";
import DefaultButton from "../src/components/DefaultButton.vue";
import AddFinanceModal from "../src/components/AddFinanceModal.vue";

export default {
  name: "App",
  data() {
    return {
      isModalOpen: false,
      transactionsList: []
    };
  },
  components: {
    DefaultTable,
    DefaultCard,
    DefaultButton,
    AddFinanceModal,
  },
  methods: {
    showModal(show) {
      var body = document.querySelector("body");
      if (show === true) {
        this.isModalOpen = true;
        body.style.overflow = "hidden";
      } else if (show === false) {
        this.isModalOpen = false;
        body.style.overflow = "auto";
      }
    },
    saveMovement(finantialMovement) {
      this.transactionsList.push(finantialMovement);
      this.showModal(false);
    }
  },
};
</script>

<style>
header {
  padding: 45px 25px;
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  padding: 50px 0;
  color: var(--black);
}

.logo {
  color: var(--primary);
  font-weight: 500;
  font-size: 2rem;
}
.logo span {
  font-weight: 300;
}
</style>
