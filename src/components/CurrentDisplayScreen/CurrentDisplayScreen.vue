<template>
        <div style="position: relative">
            <Banner style="position: relative; z-index: 3"/>
            <div style="height: 100px; background-color: white; position: relative; z-index: 3"/>
            <div class="current-display-area">
                <div class="current-display">
                    <div class="current-display-description-area">
                        <CurrentDisplayDescription v-bind:description="descriptions[0]"/>
                    </div>
                </div>
                <div class="current-display">
                    <div class="current-display-image">
                        <div class="panel-image panel-image-2"/>
                    </div>
                    <div class="current-display-description-area">
                        <CurrentDisplayDescription v-bind:description="descriptions[1]"/>
                    </div>
                </div>
                <div class="current-display">
                    <div class="current-display-image" style="z-index: 4;">
                        <div class="panel-image panel-image-3"/>
                    </div>
                    <div class="current-display-description-area">
                        <CurrentDisplayDescription id="display-description-3" v-bind:description="descriptions[2]"/>
                    </div>
                </div>
            </div>
            <div class="pin-box">
                <div class="panel-image panel-image-1">
                    <div class="seeall-button">
                        전시 모두 보기
                        <i class="fa-solid fa-chevron-right fa-xs" style="padding-left: 5px;"></i>
                    </div>
                </div>
            </div>
        </div>
</template>

<script>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import Banner from '../Banner.vue'
import CurrentDisplayDescription from './CurrentDisplayDescription.vue';

gsap.registerPlugin(ScrollTrigger)

export default {
    components: {
        Banner,
        CurrentDisplayDescription
    },
    data() {
        const descriptions = [
            {
                title: "한국 실험미술 1960-70년대",
                subTitle: "ONLY THE YOUNG",
                description1: "국립현대미술관과 미국 뉴욕 솔로몬 R. 구겐하임미술관은 «한국 실험미술 1960-70년대»<br/>(Only the Young:Experimental Art in South Korea 1960s-1970s)전을 2월 11일부터<br/>5월 12일까지 미국 LA 해머미술관에서 개최한다.",
                description2: "이번 전시는 지난 해 국립현대미술관 서울에서의 성공적인 개최에 이어, 미국 뉴욕 구겐하임<br/>미술관에서 큰 호응을 얻고 LA 해머미술관에 순회하게 되어한국 실험미술에 대한 관심을 계속<br/>이어가게 되었다.",
                period: "2월 11일 일요일 - 5월 12일 일요일",
                fee: "무료",
                location: "해외 미국 LA해머미술관",
                count: "약 80여점",
                creators: "강국진, 김구림, 김영진, 성능경,<br/>이강소, 이건용, 이승택, 최병소 등 26명",
                sponsor: "국립현대미술관, 미국 뉴욕 솔로몬<br/>R. 구겐하임미술관, 미국 LA해머미술관"
            },
            {
                title: "보이는 수장고: MMCA<br/>이건희컬렉션 해외 명작전",
                description1: "국립현대미술관 청주 미술품수장센터 ‘보이는 수장고’는 ‘수장’과 ‘전시’의 기능을 모두<br/>아우르는 새로운 개념의 미술품 수장고이다. 국립현대미술관은 ‘보이는 수장고’ 공간을<br/>재조성하고 ‘MMCA 이건희컬렉션’ 을 시리즈로 선보인다.",
                description2: "‘MMCA 이건희컬렉션’은 고(故) 이건희 삼성그룹 회장 유족으로부터 기증받은 것으로,<br/>총 1,488점의 방대한 규모를 자랑한다. 미술관은 『국립현대미술관 이건희컬렉션』 전작<br/>도록과 누리집을 통해 소장품에 대한 정보를 공개하고 있다.",
                period: "1월 30일 화요일 - 6월 30일 일요일",
                fee: "무료",
                location: "청주 2층, 보이는 수장고",
                count: "7점",
                creators: "마르크 샤갈, 살바도르 달리, 카미유<br/>피사로, 클로드 모네, 폴 고갱, 피에르<br/>오귀스트 르누아르, 호안 미로",
                sponsor: "MMCA"
            },
            {
                title: "미술관 길목 프로젝트: 정세인",
                subTitle: "WELCOME ZONE PROJECT",
                description1: "«미술관 길목 프로젝트»는 청주관의 유휴공간을 다양한 실험적 예술 작품을<br/>소개하는 공간으로 활용하는 프로젝트이다. 동시에 관람객을 로비로 자연스럽게<br/>유도하여 혼란을 막고자 만든 일종의 ‘웰컴존welcome zone’이다.",
                description2: "이번 프로젝트에 첫 번째로 선정된 작가 정세인은 타이포 설치작업과 타이포를<br/>활용한 6개의 영상작업이 이어져 메들리 형식으로 보여주는 작업을 준비했다.<br/>확장된 시각 매체-타이포그래피 설치 작업과 영상 미디어 작업을 만나볼 수 있다.",
                period: "1월 31일 수요일 - 12월 31일 화요일",
                fee: "무료",
                location: "청주 진입로 및 외벽",
                count: "7점",
                creators: "정세인",
                sponsor: "국립현대미술관"
            }
        ]
        return {
            descriptions
        }
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
        gsap.to('.panel-image-3', {
            scrollTrigger: {
                trigger: '.panel-image-3',
                endTrigger: '#display-description-3',
                start: 'top 0%',
                end: 'bottom bottom',
                pin: true,
                markers: true,
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
        position: relative;
    }
    .panel-image .seeall-button {
        width: 152px;
        height: 152px;
        border-radius: 100px;
        background-color: #e8e7e6;
        position: absolute;
        right: 37px;
        bottom: 37px;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 20px;
        font-weight: 700;
    }
    .panel-image .seeall-button:hover {
        background-color: black;
        color: white;
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
        width: 100%;
        display: flex;
        justify-content: flex-end;
        flex-direction: row;
    }
    .current-display-image {
        width: 50%;
    }
    .current-display-description-area {
        width: 50%;
        background-color: #f8f8f4;
    }
    .description-title {
        font-weight: 600;
        font-size: 50px;
    }
</style>