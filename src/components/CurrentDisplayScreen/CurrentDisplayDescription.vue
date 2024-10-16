<template>
    <div class="current-display-description">
        <div style="height: 132px"/>
        <div class="title" v-html="this.description.title"></div>
        <div class="subtitle">
            {{  this.description.subTitle }}
        </div>
        <div style="height: 53px"/>
        <div class="description" v-html="this.description.description1"/>
        <div style="height:35px"/>
        <div class="description" v-html="this.description.description2"/>
        <div style="height: 54px"/>
        <div class="divider" />
        <div style="height: 53px"/>
        <div class="content-area">
            <DescriptionContent v-bind:content="{ title: '기간', content: this.description.period }"/>
            <DescriptionContent v-bind:content="{ title: '관람료', content: this.description.fee }"/>
        </div>
        <div class="content-area">
            <DescriptionContent v-bind:content="{ title: '장소', content: this.description.location }"/>
            <DescriptionContent v-bind:content="{ title: '작품 수', content: this.description.count }"/>
        </div>
        <div class="content-area">
            <DescriptionContent v-bind:content="{ title: '작가', content: this.description.creators }"/>
            <DescriptionContent v-bind:content="{ title: '주최/후원', content: this.description.sponsor }"/>
        </div>
        <div style="height: 75px"/>
        <div style="display: flex; justify-content: center;">
            <div class="reserve-button">
                전시 관람 예약하기
            </div>
        </div>
        <div style="height:120px"/>
    </div>
</template>

<script>
import DescriptionContent from './DescriptionContent.vue';

export default {
    name: "CurrentDisplayDescription",
    props: [
        "description"
    ],
    components: {
        DescriptionContent
    }
}
</script>

<style>
    .current-display-description {
        color: #1f1907;
        width: 100%;
        white-space: nowrap;
        padding-left: 170px;
        padding-right: 150px;
    }
    .current-display-description .title {
        font-size: 50px;
        font-weight: 600;
    }
    .current-display-description .subtitle {
        font-size: 30px;
        font-weight: 400;
    }
    .current-display-description .description {
        font-size: 16px;
        font-weight: 400;
        color: #3c3b38;
        line-height: 28px;
    }
    .current-display-description .divider {
        width: 641px;
        height: 1px;
        background-color: #ebe7e7;
    }
    .current-display-description .content-area {
        padding-left: 25px;
        display: flex;
    }
    .current-display-description .reserve-button {
        width: 201px;
        height: 53px;
        background-color: black;
        color: white;
        font-size: 18px;
        font-weight: 500;
    }

</style>