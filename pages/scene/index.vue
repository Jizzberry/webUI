<template>
  <div class="content-view">
    <div class="bg-img"></div>
    <div class="grid">
      <vs-row>
        <vs-col :w="7">
          <div class="video-container"></div>
          <div>
            <VideoDetails class="mt"></VideoDetails>
          </div>
        </vs-col>
        <vs-col :w="1"></vs-col>
        <vs-col :w="3">
          <template v-for="item in upnext">
            <UpNext
              class="mb"
              :key="item"
              :title="item.file_name"
              :imgSrc="item.thumbnail"
            ></UpNext>
          </template>
        </vs-col>
        <vs-col :w="1"></vs-col>
      </vs-row>
    </div>
  </div>
</template>

<script>
import UpNext from "@/components/UpNext";
import VideoDetails from "@/components/VideoDetails";
import { BASE_URL } from "@/constants/url.js";
export default {
  layout: "navigation",
  components: {
    UpNext,
    VideoDetails,
  },

  async fetch() {
    console.log(this.$route.query);
    this.upnext = await this.$axios.$get(BASE_URL + "/api/upnext");

    //this.tmp = await this.$axios.$get(window.location.protocol + "//" + window.location.host + '/api/files');
    console.log(this.scenes);
  },

  data: () => ({
    upnext: [],
  }),
};
</script>

<style>
.content-view {
  margin-top: calc(70px + 10px);
}

.scene-detail-container {
  margin-top: 30px;
  position: relative;
  height: 100vh;
}

.video-container {
  max-height: 65vh;
  max-width: 100%;
  background-color: aqua;
}

.mb {
  margin-bottom: 40px;
}

.mt {
  margin-top: 40px;
}

.bg-img {
  position: fixed;
  width: 100vh;
  height: 100vh;
  min-height: 500px;
  right: 0;
  top: 60px;
  background-image: url(~@/assets/bg.svg);
  background-position-x: 102%;
  background-position-y: -2.4rem;
  background-attachment: fixed;
  background-repeat: no-repeat;
  background-color: rgb(250, 250, 250);
}
</style>
