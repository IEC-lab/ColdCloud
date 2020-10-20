<template>
  <div id="app_content">
    <div id="videoTitle">
      <div class="title_label">{{ selectedStreamLabel }}</div>
      <div class="title_content">{{ selectedStreamTitle }}</div>
    </div>
    <div id="videoDescription">{{ selectedStreamDescription }}</div>
    <video id="videoPlay" muted controls width="960" height="540"></video>
    <div id="resource_list"></div>
  </div>
</template>

<script>
import $ from "jquery";
var theObj = null;
export default {
  name: "App",
  data() {
    return {
      selectedStreamTitle: "",
      selectedStreamDescription: "",
      selectedStreamLabel: "",
    };
  },
  mounted: function () {
    theObj = this;
    this.videoEle = $("#videoPlay")[0];
  },
  setTitleAndDescription(title, description) {
    theObj.selectedStreamTitle = title;
    theObj.selectedStreamDescription = description;
    theObj.selectedStreamLabel = "实时流";
  },
  getVideoEle() {
    return theObj.videoEle;
  },
};
</script>

<style>
#app_content {
  position: relative;
  width: 1920px;
  height: 880px;
}
#videoTitle {
  width: 100%;
  height: 60px;
  position: relative;
}
#videoTitle .title_label {
  position: absolute;
  top: 28px;
  left: 258px;
  width: 58px;
  padding-top: 3px;
  height: 19px;
  background-color: rgb(255, 175, 201);
  color: white;
  font-size: 12px;
  text-align: center;
}
#videoTitle .title_content {
  position: absolute;
  top: 26px;
  left: 322px;
  margin-left: 8px;
  font-size: 18px;
}
#videoDescription {
  height: 34px;
  font-size: 12px;
  margin-left: 260px;
  color: rgb(153, 153, 153);
}
#videoPlay {
  margin: 0 0 0 256px;
}
#resource_list {
  position: absolute;
  right: 310px;
  top: 100px;
}
</style>
