<!-- Only logo on scroll -->

<template>
  <div>
    <TopNav class="topnav-fixed"></TopNav>
    <!-- <SecondNavBar class="second-nav"></SecondNavBar> -->
    <Sidebar class="sidebar"></Sidebar>
    <div class="vuebar-element" v-bar>
      <div>
        <div class="nuxt-container nuxt-container-shift" ref="nuxt_container">
          <nuxt />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TopNav from "@/components/TopNav";
// import SecondNavBar from "@/components/SecondNavBar";
import Sidebar from "@/components/Sidebar";
export default {
  components: {
    // SecondNavBar,
    TopNav,
    Sidebar,
  },
  mounted: function () {
    Sidebar.methods.setCallback(this.toggleSidebarCallback);
  },
  methods: {
    toggleSidebarCallback: function (isOpen) {
      const cont = this.$refs.nuxt_container;
      if (isOpen) {
        cont.classList.add("nuxt-container-shift");
      } else {
        cont.classList.remove("nuxt-container-shift");
      }
    },
  },
};
</script>

<style>
body {
  background-color: #fafafa;
}

.nuxt-container {
  z-index: 1;
  transition: all 0.25s ease;
  margin-left: 40px;
}

.nuxt-container-shift {
  margin-left: 300px;
}

.topnav-fixed {
  z-index: 4;
}

.sidebar {
  z-index: 3;
  margin-top: 70px;
  height: calc(100% - 70px);
  left: 0;
  overflow: auto;
}

.second-nav {
  z-index: 2;
  display: flex;
  position: relative;
  margin-top: 70px;
}

.vuebar-element {
  height: 100vh;
  width: 100%;
}

.vb > .vb-dragger {
  z-index: 5;
  width: 12px;
  right: 0;
}

.vb > .vb-dragger > .vb-dragger-styler {
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
  -webkit-transform: rotate3d(0, 0, 0, 0);
  transform: rotate3d(0, 0, 0, 0);
  -webkit-transition: background-color 100ms ease-out, margin 100ms ease-out,
    height 100ms ease-out;
  transition: background-color 100ms ease-out, margin 100ms ease-out,
    height 100ms ease-out;
  background-color: rgba(48, 121, 244, 0.1);
  margin: 5px 5px 5px 0;
  border-radius: 20px;
  height: calc(100% - 10px);
  display: block;
}

.vb.vb-scrolling-phantom > .vb-dragger > .vb-dragger-styler {
  background-color: rgba(255, 9, 97, 0.3);
}

.vb > .vb-dragger:hover > .vb-dragger-styler {
  background-color: rgba(255, 9, 97, 0.5);
  margin: 0px;
  height: 100%;
}

.vb.vb-dragging > .vb-dragger > .vb-dragger-styler {
  background-color: rgba(255, 9, 97, 0.5);
  margin: 0px;
  height: 100%;
}

.vb.vb-dragging-phantom > .vb-dragger > .vb-dragger-styler {
  background-color: rgba(255, 9, 97, 0.5);
}
</style>
