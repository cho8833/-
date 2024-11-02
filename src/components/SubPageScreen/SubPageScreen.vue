<template>
    <div class="sub-page">
        <div class="header-title">
            현재 전시
        </div>
        <div style="height: 109px"/>
        <div class="menu-bar">
            <div class="menu-list">
                <div class="menu">
                전체
                </div>
                <div class="menu">
                    서울
                </div>
                <div class="menu">
                    과천
                </div>
                <div class="menu">
                    덕수궁
                </div>
                <div class="menu">
                    청주
                </div>
            </div>
            <div style="height: 22px"/>
            <div class="divider"/>
        </div>
        <div style="height: 89px"/>
        <div class="current-display-section">
            <li class="current-display-item" v-for="item of currentDisplays">
                <CurrentDisplayItem v-bind:item="item"/>
            </li>
        </div>
        <div style="height: 124px"/>
        <div class="navigation">
            <span class="material-icons chevron chevron-left">chevron_left</span>
            <div style="display: flex; width: 37px; justify-content: space-between;">
                <div class="current-page">1</div>
                <div class="total-page">/</div>
                <div class="total-page">3</div>
            </div>
            <span class="material-icons chevron">chevron_right</span>
        </div>
        <div style="height: 122px"/>
        <Footer />
    </div>
</template>

<script setup>
import CurrentDisplayItem from './CurrentDisplayItem.vue'
import Footer from '../Footer.vue'
import currentDisplay1 from '@/assets/current_display1_sub.png'
import currentDisplay2 from '@/assets/current_display2_sub.png'
import currentDisplay3 from '@/assets/current_display3_sub.png'
import currentDisplay4 from '@/assets/current_display4.png'
import currentDisplay5 from '@/assets/current_display5.png'
import currentDisplay6 from '@/assets/current_display6.png'
import currentDisplay7 from '@/assets/current_display7.png'
import currentDisplay8 from '@/assets/current_display8.png'



</script>

<script>
export default {
    data() {
        const currentDisplays = [
            {
                image: currentDisplay1,
                title: "한국 실험미술 1960-70년대",
                location: "해외, 미국 LA 해머미술관",
                date: "2월 11일 일요일 - 5월 12일 일요일"
            },
            {
                image: currentDisplay2,
                title: "MMCA 이건희컬렉션 해외 명작전",
                location: "청주 2층, 보이는 수장고",
                date: "1월 30일 화요일 - 6월 30일 일요일"
            },
            {
                image: currentDisplay4,
                title: "특별수장소 «국립현대미술관 드로잉소장품»",
                location: "청주 4층, 특별수장고",
                date: "12월 14일 목요일 - 7월 31일 수요일"
            },
            {
                image: currentDisplay5,
                title: "한국의 기하학적 추상미술",
                location: "과천 1층, 1, 2 전시실 및 중앙홀",
                date: "11월 16일 목요일 - 5월 19일 일요일"
            },
            {
                image: currentDisplay6,
                title: "개방 수장고 : 전뢰진 조각ㆍ드로잉",
                location: "청주 1층, 개방수장고",
                date: "11월 7일 화요일 - 5월 26일 일요일"
            },
            {
                image: currentDisplay3,
                title: "미술관 길목 프로젝트: 정세인",
                location: "청주 진입로 및 외벽",
                date: "1월 31일 수요일 - 12월 31일 화요일"
            },
            {
                image: currentDisplay7,
                title: "한국 현대미술의 동시대성 탐험기",
                location: "서울 1층, 1전시실 및 열린 공간",
                date: "6월 16일 금요일 - 9월 8일 알요일"
            },
            {
                image: currentDisplay8,
                title: "MMCA 예술놀이마당",
                location: "어린이미술관 1층, 어린이미술관 가족라운지",
                date: "12월 28일 수요일 - 5월 31일 금요일"
            }
        ]
        return {
            currentDisplays
        }
    }
}
</script>

<style>
    .sub-page {
        width: 100%;
        padding-top: 157px;
        display: flex;
        align-items: center;
        flex-direction: column;
    }
    .sub-page .header-title {
        font-size: 35px;
        font-weight: 700;
        color: black;
    }
    .sub-page .menu-bar {
        width: 100%;
    }
    .sub-page .menu-bar .menu-list {
        display: flex;
    }
    .sub-page .menu-bar .divider {
        width: 100%;
        height: 2px;
        background-color: #d9d9d9;
    }
    .sub-page .current-display-section {
        display: grid;
        grid-template-columns: repeat(4, auto);
        column-gap: 75px;
        row-gap: 91px;
    }
    .sub-page .navigation {
        display: flex;
        font-size: 18px;
        font-weight: 700;
        text-align: center;
    }
    .sub-page .navigation .chevron-left {
        color: #babab8;
    }
    .sub-page .navigation .current-page {
        color: #a8996e;
    }
    .sub-page .navigation .total-page {
        color: #babab8;
    }
</style>