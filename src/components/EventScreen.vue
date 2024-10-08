<template>
    <div class="event-screen">
        <div style="width: 100%">
            <div class="event-screen-title">
                진행 중인 전시
            </div>
            <div style="height: 25px"/>
            <div class="category-button-container">
                <li class="category-button-list" v-for="(item, index) in categories">
                    <div class="category-button" :class="selectedCategoryIndex === index ? selectedCategoryClass : ''" @click="onCategoryClick(index)">
                        {{ item }}
                    </div>
                </li>
            </div>
        </div>
        <div style="height: 18px"/>
        <div class="display-container">
            <div class="display-all">
                <div class="display-all-text">
                    전시 모두 보기
                </div>
                <span class="material-icons display-all-chevron">chevron_right</span>
            </div>
            <div style="height: 24px"/>
            <div style="display: flex">
                <li style="list-style-type: none;" v-for="(item, index) in displaies">
                    <div style="display:flex">
                        <div>
                            <img :src="item.image">
                            <div style="height: 24px"/>
                            <div class="display-text-description">
                                {{ item.description }}
                            </div>
                            <div style="height: 10px"/>
                            <div class="display-text-title">
                                {{  item.title }}
                            </div>
                        </div>
                        <div v-if="index < displaies.length" style="width: 50px;"/>
                    </div>
                </li>
            </div>
        </div>
        <div class="more-display" v-if="isMore">
            <div style="height: 90px"/>
            <div style="display: flex">
                <li style="list-style-type: none;" v-for="(item, index) in moreDisplaies">
                    <div style="display:flex">
                        <div>
                            <img :src="item.image">
                            <div style="height: 24px"/>
                            <div class="display-text-description">
                                {{ item.description }}
                            </div>
                            <div style="height: 10px"/>
                            <div class="display-text-title">
                                {{  item.title }}
                            </div>
                        </div>
                        <div v-if="index < displaies.length" style="width: 50px;"/>
                    </div>
                </li>
            </div>
        </div>
        <div style="height: 68px"/>
        <div class="display-more-button" @click="triggerMore" :class="[isMore ? displayMoreButtonExpandedClass : '']">
            <span class="material-icons more-button-chevron">
                keyboard_arrow_down
            </span>
        </div>

    </div>
</template>

<script>
import { ref } from 'vue'
import displayImage1 from '@/assets/display1.png'
import displayImage2 from '@/assets/display2.png'
import displayImage3 from '@/assets/display3.png'
import displayImage4 from '@/assets/display4.png'
import displayImage5 from '@/assets/display5.png'
import displayImage6 from '@/assets/display6.png'

export default {
    data() {
        const categories = ["전체", "전시", "필름앤비디오", "다원예술", "해외전시"]

        const displaies = [
            {
                image: displayImage1,
                description: "청주 / 12월 14일 목요일 - 7월 31일 수요일",
                title: "특별수장소 «국립현대미술관 드로잉소장품»",
            },
            {
                image: displayImage2,
                description: "청주 / 11월 7일 화요일 - 5월 26일 일요일",
                title: "국립현대미술관 청주 개방 수장고 : 전뢰진 조각ㆍ드로잉"
            },
            {
                image: displayImage3,
                description: "과천 / 11월 16일 목요일 - 5월 19일 일요일",
                title: "한국의 기하학적 추상미술"
            }
        ]
        const moreDisplaies = [
            {
                image: displayImage4,
                description: "청주 / 1월 31일 수요일 - 12월 31일 화요일",
                title: "청주 진입로 및 외벽"
            },
            {
                image: displayImage5,
                description: "서울 / 6월 16일 금요일 - 9월 8일 알요일",
                title: "한국 현대미술의 동시대성 탐험기"
            },
            {
                image: displayImage6,
                description: "어린이미술관 / 12월 28일 수요일 - 5월 31일 금요일",
                title: "MMCA 예술놀이마당"
            }
        ]
        return {
            categories,
            displaies,
            moreDisplaies
        }
    },
    setup() {
        const selectedCategoryIndex = ref(0)
        const selectedCategoryClass = ref("category-button-selected")
        const displayMoreButtonExpandedClass = ref('display-more-button-expanded')
        const isMore = ref(false)
        return {
            selectedCategoryIndex,
            selectedCategoryClass,
            displayMoreButtonExpandedClass,
            isMore
        }
    },
    methods: {
        onCategoryClick(index) {
            this.selectedCategoryIndex = index;
        },
        triggerMore() {
            this.isMore = !this.isMore;
        }
    }
}
</script>
<style>
    .event-screen {
        padding-left: 149px;
        padding-right: 149px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .event-screen-title {
        font-size: 35px;
        font-weight: 700;
    }
    .category-button-container {
        display: flex;
        flex-direction: row;
    }
    .category-button-list {
        list-style-type: none;
        margin-right: 11px;
    }
    .category-button {
        padding-left: 27px;
        padding-right: 27px;
        padding-top: 15px;
        padding-bottom: 15px;
        border-radius: 22px;
        border-style: solid;
        border-width: 1px;
        border-color: #e4e2dd;
        color: #989690;
        transition: all 0.3s ease;
    }
    .category-button-selected,
    .category-button:hover {
        background-color: black;
        color: white;
    }

    .display-container {
        padding-left: 52px;
        padding-right: 52px;
    }
    .display-all {
        display: flex;
        justify-content: flex-end;
    }
    .display-all-text {
        font-size: 20px;
        font-weight: 700;
    }
    .display-text-description {
        font-size: 16px;
        color: #998a5f;
    }
    .display-text-title {
        font-size: 20px;
        font-weight: 600;
    }
    .display-more-button {
        width: 55px;
        height: 55px;
        border-radius: 99px;
        background-color: #e8e7e6;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all 0.3s;
    }
    .more-button-chevron {
        font-size: 32px;
    }
    .display-more-button-expanded {
        transform: rotate(180deg)
    }
    .display-more {
        transition: all 0.3s ease;
        overflow: hidden;
    }
</style>