<template>
  <div id="app_header">
    <div class="indent_px24"></div>
    <img src="./assets/iec_log.jpg" class="vertical_middle" width="40px" />
    &nbsp;&nbsp;
    <strong class="vertical_middle">Cold Cloud（IEC 云边端架构前台）</strong>
    <div class="line_px3 absolute_left0_bottom0"></div>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
#app_header{
  width: 1920px;
  height: 52px;
  padding-top: 7px;
  position: relative;
  background-color: white;
}
.absolute_left0_bottom0{
  position: absolute;
  left: 0;
  bottom: 0;
}
.line_px3{
  width: 100%;
  height: 3px;
  background-color: rgb(243,243,243);
}
.vertical_middle{
  vertical-align: middle;
}
.indent_px24{
  display: inline-block;
  width: 24px;
}
</style>
