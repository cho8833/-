<template>
        <div style="position: relative">
            <Banner style="position: relative; z-index: 3"/>
            <div style="height: 100px; background-color: white; position: relative; z-index: 3"/>
            <div class="current-display-area">
                <div class="current-display">
                    <div class="current-display-description">
                        <div style="height: 132px"/>
                        <div class="description-title">
                            한국 실험미술 1960-70년대
                        </div>
                    </div>
                </div>
                <div class="current-display">
                    <div class="current-display-image">
                        <div class="panel-image panel-image-2"/>
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
                </div>
                <div class="current-display">
                    <div class="current-display-image" style="z-index: 4;">
                        <div class="panel-image panel-image-3"/>
                    </div>
                    <div class="current-display-description">
                        <div style="height: 132px"/>
                        <div class="description-title">
                            미술관 길목 프로젝트: 정세인
                        </div>
                    </div>
                </div>
            </div>
            <div class="pin-box">
                <div class="panel-image panel-image-1"></div>
            </div>
        </div>
</template>

<script>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import Banner from './Banner.vue'

gsap.registerPlugin(ScrollTrigger)

export default {
    components: {
        Banner
    },
    mounted() {
       gsap.utils.toArray(".panel-image-1").forEach((panel, i) => {
          ScrollTrigger.create({
            trigger: panel,
              start: "top 0%",
            end: "bottom bottom",
            endTrigger: '.panel-image-2',
            pin: true,
            pinSpacing: false
          });
       });
        gsap.to('.panel-image-2', {
            scrollTrigger: {
                trigger: '.panel-image-2',
                endTrigger: '.panel-image-3',
                start: 'top 0%',
                end: 'bottom bottom',
                pin: true,
                pinSpacing: false
            }
       })
    }
}


</script>

<style>
    .pin-box {
        width: 50%;
        position: absolute;
        top: 0;
        z-index: 2;
    }
    .panel-image {
        height: 100vh;
    }
    .panel-image-1 {

        background: url('@/assets/current_display1.png') no-repeat;
        background-size: cover;
    }
    .panel-image-2 {   
        background: url('@/assets/current_display2.png') no-repeat;
        background-size: cover;
    }
    .panel-image-3 {
        width: 100.1%;
        background: url('@/assets/current_display3.png') no-repeat;
        background-size: cover;
    }
    .current-display-area {
        width: 100%;
        position: relative;
        display: flex;
        align-items: flex-end;
        flex-direction: column;
        z-index: 3;
    }
    .current-display {
        height: 100vh;
        width: 100%;
        display: flex;
        justify-content: flex-end;
        flex-direction: row;
    }
    .current-display-image {
        width: 50%;
    }
    .current-display-description {
        width: 50%;
        background-color: #f8f8f4;
        padding-left: 170px;
    }
    .description-title {
        font-weight: 600;
        font-size: 50px;
    }
</style>