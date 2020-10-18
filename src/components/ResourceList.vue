<template>
  <div id="resource_list">
    <p id="resource_list_title">可选数据流</p>
    <div class="resource_container">
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
        <div class="one_resource">
            <div class="resource_title">数据流标题</div>
            <div class="resource_description">数据流描述</div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ResourceList'
}
</script>

<style>
#resource_list{
    width: 292px;
    height: 502px;
    padding: 14px;
    background-color: rgb(244, 244, 244);
}
#resource_list_title{
    font-size: 18px;
    font-weight: bold;
    margin-bottom: 14px;
}
#resource_list .resource_container{
    width: 100%;
    height: 476px;
    overflow-x: auto;
}
#resource_list .one_resource{
    padding: 5px 5px 5px 5px;
    cursor: pointer;
}
#resource_list .one_resource:hover{
    background-color: white;
}
#resource_list .resource_title{
    font-size: 14px;
}
#resource_list .resource_description{
    font-size: 12px;
    color: rgb(153, 153, 153);
}
</style>

