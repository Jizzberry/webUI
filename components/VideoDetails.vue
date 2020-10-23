<template>
  <div>
    <div class="videodetails-container htop">
      <div><span>Cast:</span></div>
      <div><span>Tags:</span></div>
      <div><span>Studios:</span></div>
    </div>
    <div class="videodetails-container hbottom bottom-container">
      <div><span>Path:</span></div>
      <div><span>Date Created:</span></div>
      <div><span>Size:</span></div>
      <div><span>Length:</span></div>
    </div>
  </div>
</template>

<style>
.videodetails-container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 100%;
  border: 1px solid #000000;
  box-sizing: border-box;
  border-radius: 29px;
  padding-left: 23px;
  padding-top: 20px;
  padding-bottom: 20px;
}

.bottom-container {
  margin-top: 40px;
}

.htop {
  height: calc(
    (3 * 21px) /* 3 elements */ + (4 * 21px) /* spacing between them */
  );
}

.hbottom {
  height: calc(
    (4 * 21px) /* 4 elements */ + (5 * 21px) /* spacing between them */
  );
}
</style>