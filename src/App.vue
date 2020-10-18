<template>
  <div id="app_content">
      <div id="videoTitle">
        <div class="title_label">实时流</div><div class="title_content">{{ selectedStreamTitle }}</div>
      </div>
      <div id="videoDescription">{{ selectedStreamContent }}</div>
      <video id="videoPlay" muted controls width="960" height="540"></video>
  </div>
</template>

<script>
import $ from "jquery";
import Common from "@/components/Common";
import flvjs from "flv.js";
import graphqlHelper from "@/pkg/Graphql";

export default {
  name: "App",
  data() {
    var rs = graphqlHelper.queryGraphql(`query Query { frameStreams { URL Position } }`);
    var oneUrl = "";
    var oneTitle = "";
    var oneContent = "";
    if(rs != null){
      var selectedStream = rs.frameStreams[1];
      oneUrl = selectedStream["URL"];
      oneTitle = selectedStream["Position"];
      oneContent = oneUrl;
    }
    return {
      selectedStreamURL: oneUrl,
      selectedStreamTitle: oneTitle,
      selectedStreamContent: oneContent,
    };
  },
  mounted: function () {
    var theObj = this;
    var videoPlay = $("#videoPlay")[0];

    if (flvjs.isSupported()) {
      theObj.player = flvjs.createPlayer({
        type: "flv",
        isLive: true,
        url: `${Common.COLDBRIDGEURL}?url=${theObj.selectedStreamURL}`,
      });
      theObj.player.attachMediaElement(videoPlay);
      try {
        theObj.player.load();
        theObj.player.play();
      } catch (error) {
        console.log(error);
      }
    } else {
      alert("flvjs isn't supported");
    }
  },
};
</script>

<style>
#videoTitle{
  width: 100%;
  height: 60px;
  position: relative;
}
#videoTitle .title_label{
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
#videoTitle .title_content{
  position: absolute;
  top: 26px;
  left: 322px;
  margin-left: 8px;
  font-size: 18px;
}
#videoDescription{
  height: 34px;
  font-size: 12px;
  margin-left: 260px;
  color: rgb(153, 153, 153);
}
#videoPlay{
  margin: 0 0 0 256px;
}
</style>
