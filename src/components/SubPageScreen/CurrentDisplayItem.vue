<template>
    <div class="current-display-item">
        <div class="image-area">
            <div class="image-mouseover">
                자세히 보기
            </div>
            <img class="image" :src="this.item.image">
        </div>
        <div style="height: 28px"/>
        <div class="title">
            {{  item.title  }}
        </div>
        <div style="height: 10px"/>
        <div class="location">
            {{ item.location }}
        </div>
        <div style="height:16px"/>
        <div class="date">
            {{ item.date }}
        </div>
    </div>
</template>

<script>

export default {
    name: "CurrentDisplayItem",
    props: [
        "item"
    ],
}
</script>

<style>
    .current-display-item {
        list-style-type: none;
        position: relative;
    }
    .current-display-item .image-area {
        position: relative;
    }
    .current-display-item .image-area:hover >.image-mouseover {
        opacity: 1;

    }
    .current-display-item .image-area .image {
        width: 348px;
        height: 507px;
        object-fit: cover;
    }

    .current-display-item .image-area .image-mouseover {
        position: absolute;
        bottom: 0;
        width: 100%;
        text-align: center;
        background-color: black;
        color: white;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 9px 0px;
        opacity: 0;
    }
    
    .current-display-item .title {
        font-size: 20px;
        font-weight: 600;
        color: black;
    }
    .current-display-item .location {
        color: #2d2d2d;
        font-size: 16px;
        font-weight: 500;
    }
    .current-display-item .date {
        color: #998a5f;
        font-size: 16px;
        font-weight: 400;
    }
</style>