<template>
  <header class="container">
    <div class="row align-items-center justify-content-between h-100">
      <div class="col-4">
        <img class="" src="../assets/images/Logonetflix.png" alt="" />
      </div>
      <div class="col-8 col-md-4">
        <div class="input-group input-group-sm d-flex justify-content-end">
          <input
            type="text"
            class="form-control"
            placeholder="Cerca per titolo"
            aria-label="Recipient's username"
            aria-describedby="button-addon2"
            v-model="search"
            @keyup.enter="$emit('performSearch', search)"
          />
          <button
            class="btn btn-outline-secondary"
            type="button"
            id="button-addon2"
            @click="find"
          >
            Cerca
          </button>
        </div>
      </div>
    </div>
  </header>
</template>
<script>
export default {
  components: {},
  name: "AppHeader",
  data() {
    return {
      search: "",
    };
  },
  methods: {
    find() {
      this.$emit("performSearch", this.search);
      this.search = "";
    },
  },
  computed: {},
};
</script>

<style lang="scss">
@import "../style/generals.scss";

img {
  height: 40px;
}

header {
  height: 50px;
  background-color: $bg-navbar;
}
</style>
