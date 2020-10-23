<template>
  <div class="search-container">
    <form class="searchbox" autocomplete="off">
      <input
        type="search"
        placeholder="Search..."
        name="search"
        class="searchbox-input searchbar-font searchbar-round"
        required
      />
    </form>
  </div>
</template>

<script>
export default {
  mounted: function () {},

  methods: {},
};
</script>

<style>
.search-container {
  position: absolute;
  display: flex;
  width: 30%;
  height: 55%;
  transform: translateX(-13.5%);
}

.searchbox {
  flex: auto;
  display: block;
  height: 100%;
}

.searchbar-font {
  font-size: 18px;
  font-weight: 500;
}

.searchbar-round {
  border: none;
  border-radius: 8px;
  background: #e3e3e3;
}

.searchbox-input {
  display: block;
  text-align: center;
  width: 100%;
  height: 100%;
}

input::placeholder {
  color: #545454;
}
</style>
