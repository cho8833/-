<template>
    <div class="description-content-box">
        <div class="content-title">
            {{ content.title }}
        </div>
        <div style="height: 12px"/>
        <div class="content" v-html="this.content.content">
        </div>
    </div>
</template>
<script>
export default {
    name: "DescriptionContent",
    props: [
        "content"
    ]
}
</script>

<style>
    .description-content-box {
        width: 334px;
        height: 79px;
    }
    .description-content-box .content-title {
        font-size: 18px;
        font-weight: 600;
    }
    .description-content-box .content {
        font-size: 16px;
        font-weight: 400;
        line-height: 24px;
        color: #444035;
    }
</style>