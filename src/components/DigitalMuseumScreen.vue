<template>
    <div class="digital-museum-screen">
        <div class="top">
            <div class="title">
            디지털 미술관
            </div>
            <div style="height: 31px"/>
            <div class="description">
                MMCA 소장품, 큐레이터 전시 해설, 강의 및 학술 토론 등을
            </div>
            <div class="description">
                디지털 미술관의 생생한 영상과 VR을 통해 함께하세요.
            </div>
            <div class="seeall-button">
                디지털미술관 모두 보기
                <span class="material-icons chevron">chevron_right</span>
            </div>
        </div>
        <div style="height: 80px;"/>
        <div class="video-list">
            <li class="video-item" v-for="item of videos">
                <img class="video" :src="item.video">
                <div style="height: 20px"/>
                <div class="author">
                    {{ item.author }}
                </div>
                <div style="height: 11px;"/>
                <div class="title">
                    {{  item.title  }}
                </div>
            </li>
        </div>
    </div>

</template>

<script>
import video1 from '@/assets/digital_museum_video1.png'
import video2 from '@/assets/digital_museum_video2.png'
import video3 from '@/assets/digital_museum_video3.png'

export default {
    data() {
        const videos = [
            {
                author: "MMCA TV",
                title: "이건희 컬렉션 ｜ 국립현대미술관 소장품이 되기까지",
                video: video1
            },
            {
                author: "MMCA TV",
                title: "MMCA VR ｜ Edisode 6. 박이소",
                video: video2
            },
            {
                author: "MMCA TV",
                title: "오늘, 이작품 ｜ 전성우 : 광배만다라, 색동만다라 (1991, 1968)",
                video: video3
            },
            {
                author: "MMCA TV",
                title: "이건희 컬렉션 ｜ 국립현대미술관 소장품이 되기까지",
                video: video1
            },
            {
                author: "MMCA TV",
                title: "MMCA VR ｜ Edisode 6. 박이소",
                video: video2
            },
        ]
        return {
            videos
        }
    }
}
</script>

<style>
    .digital-museum-screen {
        padding-left: 150px;
    }
    .digital-museum-screen .top {
        position: relative;
    }
    .digital-museum-screen .top .title {
        font-size: 35px;
        font-weight: 700;
    }
    .digital-museum-screen .top .description {
        color: #646157;
        font-size: 20px;
        font-weight: 400;
    }
    .digital-museum-screen .top .seeall-button {
        width: 235px;
        height: 54px;
        border-radius: 27px;
        border-width: 2px;
        border-style: solid;
        border-color: black;
        position: absolute;
        right: 150px;
        bottom: 0;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 20px;
        font-weight: 700;
    }
    .digital-museum-screen .top .seeall-button .chevron {
        width: 16px;
        overflow: hidden;
    }
    .digital-museum-screen .video-list {
        white-space: nowrap;
        overflow-x: scroll;
        display: flex;
        list-style-type: none;
    }
    .digital-museum-screen .video-list::-webkit-scrollbar {
        height: 2px;
        background-color: #dbdbdb;
    }
    .digital-museum-screen .video-list::-webkit-scrollbar-thumb {
        background-color: black;
    }
    .digital-museum-screen .video-list .video-item {
        width: 718px;
        margin-right: 20px;
        margin-bottom: 88px;
    }
    .digital-museum-screen .video-list .video-item .video {
        height: 409px;
    }
    .digital-museum-screen .video-list .video-item .author {
        color: #a8996e;
        font-weight: 600;
        font-size: 16px;
    }
    .digital-museum-screen .video-list .video-item .title {
        color: black;
        font-weight: 700;
        font-size: 20px;
    }
</style>