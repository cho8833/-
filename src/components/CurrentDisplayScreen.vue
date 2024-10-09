<template>
    <div style="display: flex">
        <div class="current-display-image-area">
            <div class="panel-image panel-image-1">
            </div>
            <div class="panel-image panel-image-2">
            </div>
            <div class="panel-image panel-image-3">
            </div>
        </div>
        <div class="current-display-description-area">
            <div class="current-display-description">
                <div style="height: 132px"/>
                <div class="description-title">
                    한국 실험미술 1960-70년대
                </div>
            </div>
            <div class="current-display-description">
                <div style="height: 132px"/>
                <div class="description-title">
                    보이는 수장고: MMCA
                </div>
                <div class="description-title">
                    이건희컬렉션 해외 명작전
                </div>
            </div>
            <div class="current-display-description">
                <div style="height: 132px"/>
                <div class="description-title">
                    미술관 길목 프로젝트: 정세인
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

export default {
    mounted() {
        gsap.to(".panel-image-1", {
            height: "100vh",
            scrollTrigger: {
                trigger: ".panel-image-1",
                start: "center center", // 스크롤 시작 위치
                end: "bottom top", // 스크롤 종료 위치
                scrub: true, // 스크롤에 따라 애니메이션 진행
            }
        });
    }
}


</script>

<style>
    .current-display-image-area {
        position: relative;
    }
    .panel-image {
        background-size: cover;
        width: 958px;
        overflow: hidden;
        position: sticky;
        top: 0;
        left: 0;
        display: flex;
        justify-content: center;
    }
    .panel-image-1 {
        height: 50vh;
        transform-origin: top;
        background-image: url('@/assets/current_display1.png');
    }
    .panel-image-2 {   
        height: 100vh;
        background-image: url('@/assets/current_display2.png');
    }
    .panel-image-3 {
        height: 100vh;
        background-image: url('@/assets/current_display3.png');
    }
    .current-display-description-area {
        width: 100%;
        background-color: #f8f8f4;
    }
    .current-display-description {
        height: 100vh;
        padding-left: 170px;
    }
    .description-title {
        font-weight: 600;
        font-size: 50px;

    }
</style>