<template>
  <div class="upnext-container">
    <vs-row class="full-height">
      <vs-col :w="5" class="full-height">
        <div class="upnext-img-container">
          <img :src="BASE_URL + '/thumbnails/' + imgSrc" class="upnext-img" />
        </div>
      </vs-col>
      <vs-col :w="7">
        <div class="upnext-title-holder">{{ title }}</div>
      </vs-col>
    </vs-row>
  </div>
</template>

<script>
import { BASE_URL } from "@/constants/url.js";
export default {
  created() {
    this.BASE_URL = BASE_URL;
  },
  props: {
    title: {
      type: String,
      default: "Unknown",
    },
    imgSrc: {
      type: String,
      default: require("@/assets/test_img.svg"),
    },
  },
};
</script>

<style>
.upnext-container {
  position: relative;
  background-color: #ffffff;
  border: 1px solid #969696;
  width: 110%;
  height: 120px;
  box-sizing: border-box;
  border-radius: 12px;
  margin-left: calc(-5%);
}

.upnext-img-container {
  width: 100%;
  height: 100%;
  padding-bottom: 10px;
  padding-top: 10px;
  padding-left: 10px;
}

.upnext-img {
  width: 100%;
  height: 100%;
  background: #c4c4c4;
  border-radius: 11px;
}

.full-height {
  height: 100%;
}

.upnext-title-holder {
  padding-top: 10px;
  padding-left: 15px;
}
</style>