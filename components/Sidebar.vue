<template>
  <vs-sidebar
    fixed
    v-model="active"
    square
    :open.sync="$store.state.sidebar.isOpen"
  >
    <template #logo>
      <p class="sidebar-logo">Jizzberry</p>
    </template>
    <vs-sidebar-item id="home" to="/home">
      <template #icon>
        <i class="bx bx-home navbar-item"></i>
      </template>
      <span class="navbar-item"> Home </span>
    </vs-sidebar-item>
    <vs-sidebar-item id="actors">
      <template #icon>
        <i class="bx bxs-group navbar-item"></i>
      </template>
      <span class="navbar-item"> Actors </span>
    </vs-sidebar-item>
    <vs-sidebar-item id="categories">
      <template #icon>
        <i class="bx bxs-purchase-tag navbar-item"></i>
      </template>
      <span class="navbar-item"> Categories </span>
    </vs-sidebar-item>
    <template #footer>
      <div class="footer-item">
        <vs-sidebar-item id="settings">
          <template #icon>
            <i class="bx bx-cog"></i>
          </template>
          <span> Settings </span>
        </vs-sidebar-item>
      </div>
    </template>
  </vs-sidebar>
</template>

<script>
import { mapMutations } from "vuex";

export default {
  methods: {
    toggleSide: function (isOpen) {
      if (this.callback !== undefined) {
        this.callback(isOpen);
      }
    },

    setCallback: function (callback) {
      this.callback = callback;
    },
  },

  data: () => ({
    active: "home",
    callback: undefined,
  }),
};
</script>

<style>
@font-face {
  font-family: "Raleway-Medium";
  src: url("~@/assets/Raleway-Medium.ttf") format("font-truetype");

  font-weight: normal;
  font-style: normal;
}

.sidebar-logo {
  margin-top: 12px;
  font-size: 27px;
  font-weight: 400;
  font-family: "Raleway-Medium";
}

.navbar-item {
  margin-left: 15px;
}

.footer-item {
  margin-left: -10px;
}
</style>
