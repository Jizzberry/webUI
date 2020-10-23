<template>
  <div class="videocard-container">
    <div class="thumbnail-container">
      <img :src="BASE_URL + '/thumbnails/' + imgSrc" class="thumbnail" />
    </div>

    <span class="video-title">
      {{ title }}
    </span>
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
.videocard-container {
  position: relative;
  background-color: white;
  height: 25vh;
  border-radius: 21px;
  box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.2), 0 0px 12px 0 rgba(0, 0, 0, 0.19);
  margin-right: 40px;
  margin-bottom: 40px;
  overflow: hidden;
}

.thumbnail {
  width: 100%;
}

.thumbnail-container {
  height: 75%;
  background-color: blanchedalmond;
  border-radius: 20px 20px 0px 0px;
  margin-bottom: 8px;
  overflow: hidden;
}

.videocard-title {
  margin-left: 18px;
  font-weight: 500;
}
</style>
