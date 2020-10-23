<template>
  <div class="center examplex top-container">
    <vs-navbar
      text-white
      :color="active"
      fixed
      square
      center-collapsed
      v-model="active"
    >
      <template #left>
        <div class="logo-holder">
          <img
            src="@/assets/nav_toggle.svg"
            class="nav-toggle"
            v-on:click="toggleSide"
          />
          <Logo class="jizzberry-logo"></Logo>
          <TextLogo class="jizzberry-logo-text"></TextLogo>
        </div>
      </template>
      <client-only>
        <Search></Search>
      </client-only>
      <template #right>
        <ProfilePic></ProfilePic>
      </template>
    </vs-navbar>
  </div>
</template>

<script>
import Logo from "@/components/Logo";
import TextLogo from "@/components/TextLogo";
import Search from "@/components/Search";
import ProfilePic from "@/components/ProfilePic";
import Sidebar from "@/components/Sidebar";
import { mapMutations } from "vuex";
export default {
  components: {
    Logo,
    TextLogo,
    Search,
    ProfilePic,
  },
  data: () => ({
    active: "#FFFFFF",
  }),
  methods: {
    ...mapMutations({
      toggle: "sidebar/toggle",
    }),

    toggleSide: function () {
      this.toggle();
      Sidebar.methods.toggleSide(this.$store.state.sidebar.isOpen);
    },
  },
};
</script>

<style>
.nav-toggle {
  height: 20px;
  width: 20px;
  align-self: center;
  margin-right: 15px;
}

.logo-holder {
  display: flex;
  margin: 5px;
}

.jizzberry-logo {
  height: 60px;
  width: 60px;
}

.jizzberry-logo-text {
  height: 60px;
  width: 160px;
}

.top-container {
  position: relative;
}
</style>
