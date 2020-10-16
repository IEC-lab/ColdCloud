<template>
  <div id="app_content">
    <center>
      <video id="testVideo" muted controls width="960" height="540"></video>
    </center>
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
    var rs = graphqlHelper.queryGraphql(`query Query { frameStreams { URL } }`);
    var oneUrl = "";
    if(rs != null){
      oneUrl = rs.frameStreams[0]["URL"];
    }
    return {
      testUrl: oneUrl,
    };
  },
  mounted: function () {
    var theObj = this;
    var testVideo = $("#testVideo")[0];

    if (flvjs.isSupported()) {
      theObj.player = flvjs.createPlayer({
        type: "flv",
        isLive: true,
        url: `${Common.COLDBRIDGEURL}?url=${theObj.testUrl}`,
      });
      theObj.player.attachMediaElement(testVideo);
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
</style>
