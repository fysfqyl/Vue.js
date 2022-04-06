<template>
<div class="blog">
    <h5>{{title}}</h5>
    <span>{{time}}</span>
    <div>{{content}}</div>
</div>
</template>

<script>
export default {
    // 从App.vue传入数据
    props:["title","time","content"]
}

</script>

<style>
    .blog{
        width: 200px;
        border: 1px solid #555;
        background-color: rgb(180, 224, 252);
        border-radius: 10px;
        text-align: left;
        padding: 10px;
        margin-top: 10px;
    }
    .blog span{
        float:right;
        margin-top:-40px;
    }
</style>