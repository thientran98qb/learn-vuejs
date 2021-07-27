<template>
  <div>
    <button @click="onToggleModal">Toogle/Hide</button>

    <teleport to="body">
      <card-modal
        title="Cart is the one most"
        footer="footer1"
        v-if="isShowModal"
        @cancel="onToggleModal"
      >
        <template v-slot:header>
          <div>Header</div>
        </template>
        <template v-slot:footer>
          <div>
            <button @click="onToggleModal">Cancel</button>
          </div>
        </template>
      </card-modal>
    </teleport>
  </div>
</template>
<script>
import Card from "./components/Card.vue";

export default {
  name: "App",
  components: {
    CardModal: Card,
  },
  data() {
    return {
      isShowModal: false,
    };
  },
  methods: {
    onToggleModal() {
      console.log("12");
      this.isShowModal = !this.isShowModal;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
