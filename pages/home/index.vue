<template>
  <div class="content-view">
    <div class="title-holder">
      <h1 class="title">Scenes</h1>
    </div>

    <p v-if="$fetchState.pending">Fetching posts...</p>
    <p v-else-if="$fetchState.error">
      Error while fetching posts: {{ $fetchState.error.message }}
    </p>
    <div v-else class="grid" :key="item">
      <vs-row v-for="item in scenes" :key="item">
        <vs-col :w="3" v-for="scene in item" :key="scene">
          <VideoCard
            :title="scene.file_name"
            :imgSrc="scene.thumbnail"
          ></VideoCard>
        </vs-col>
      </vs-row>
    </div>
  </div>
</template>

<script>
import VideoCard from "@/components/VideoCard";
import { BASE_URL } from "@/constants/url.js";

export default {
  layout: "navigation",

  components: {
    VideoCard,
  },

  async fetch() {
    console.log(this.$route.query);
    let tmp = await this.$axios.$get(BASE_URL + "/api/files");
    this.sortScenes(tmp);
    console.log(this.scenes);
  },

  data: () => ({
    scenes: [],
  }),

  methods: {
    sortScenes: function (tmp) {
      if (tmp.length < 4) {
        this.scenes.push(tmp);
        return;
      }

      let tmpArr = [];
      for (let i = 1; i <= tmp.length; i++) {
        tmpArr.push(tmp[i - 1]);
        if (i % 4 == 0) {
          this.scenes.push(tmpArr);
          tmpArr = [];
        }
      }
      if (tmpArr.length > 0) {
        this.scenes.push(tmpArr);
      }
    },
  },
};
</script>

<style>
.content-view {
  margin-top: calc(70px + 10px);
}

.title-holder {
  margin-top: 60px;
}

.title {
  font-family: "Raleway-Medium";
  font-size: 28px;
  font-weight: 300;
}

.grid {
  margin-top: 60px;
}
</style>
