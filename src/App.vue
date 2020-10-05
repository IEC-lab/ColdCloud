<template>
  <div id="app_content">
    <center>
      <video id="testVideo" class="video-js vjs-default-skin vjs-big-play-centered" muted controls preload="auto" width="960" height="540" data-setup='{}'>
        <source :src="testUrl" type="application/x-mpegURL">
      </video>
    </center>
  </div>
</template>

<script>
import $ from 'jquery'
import Common from '@/components/Common'

export default {
  name: 'App',
  data(){
    var oneUrl = ""
    $.ajax({
      type: "GET",
      async: false,
      url: Common.STREAMSURL,
      success: function(data){
        oneUrl = data.streams[0]
      },
      error: function(err){
        console.log(err.status)
        console.log(err.responseText)
      }
    })
    return{
      testUrl: oneUrl
    }
  },
  mounted: function(){
    var theObj = this
    var testVideo = $("#testVideo")[0]

    setTimeout(function(){
      testVideo.play()
    }, 300)
  }
}
</script>

<style>
</style>
