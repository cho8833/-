<template>
    <div class="header">
        <div style="width: 91px;"/>
        <a href="/">
            <img :src="logo">
        </a>
        <div style="width: 56px"/>
        <div class="menu-bar">
            <div class="menu-list" v-on:mouseover="showMenu" v-on:mouseleave="removeMenu">
                <div class="menu" style="width: 156px;" v-on:mouseover="showUnderline" v-on:mouseleave="removeUnderline">
                    <div class="cube">
                        <div class="face front">
                            관람ㆍ참여
                        </div>
                        <div class="face back">
                            VisitㆍParticipation
                        </div>
                    </div>                    
                    <Transition name="menu-fade" class="transition">
                        <div v-if="expandMenu" >
                            <div style="height: 58px"/>
                            <li class="sub-menu" v-for="(item, index) in menuList1">
                                <a class="sub-menu-item cube" href="/sub-page">
                                    <div class="face front">
                                        {{ item.kor }}
                                    </div>
                                    <div class="face back" style="top: 8px;">
                                        {{ item.eng }}
                                    </div>
                                </a>
                            </li>
                        </div>
                    </Transition>
                </div>
                <div class="menu" style="width: 151px" v-on:mouseover="showUnderline" v-on:mouseleave="removeUnderline">
                    <div class="cube">
                        <div class="face front">
                            전시
                        </div>
                        <div class="face back">
                            Exhibition
                        </div>
                    </div>
                    <Transition name="menu-fade" class="transition">
                        <div v-if="expandMenu" >
                            <div style="height: 58px"/>
                            <li class="sub-menu" v-for="(item, index) in menuList2">
                                <div class="sub-menu-item cube">
                                    <div class="face front">
                                        {{ item.kor }}
                                    </div>
                                    <div class="face back" style="top: 8px;">
                                        {{ item.eng }}
                                    </div>
                                </div>
                            </li>
                        </div>
                    </Transition>
                </div>
                <div class="menu" style="width:112px" v-on:mouseover="showUnderline" v-on:mouseleave="removeUnderline">
                    <div class="cube">
                        <div class="face front">
                            교육
                        </div>
                        <div class="face back">
                            Education
                        </div>
                    </div>
                    <Transition name="menu-fade" class="transition">
                        <div v-if="expandMenu" >
                            <div style="height: 58px"/>
                            <li class="sub-menu" v-for="(item, index) in menuList3">
                                <div class="sub-menu-item cube" v-on:click="setSubPageScreen">
                                    <div class="face front">
                                        {{ item.kor }}
                                    </div>
                                    <div class="face back" style="top: 8px;">
                                        {{ item.eng }}
                                    </div>
                                </div>
                            </li>
                        </div>
                    </Transition>
                </div>
                <div style="width: 7px"/>
                <div class="menu" style="width:108px" v-on:mouseover="showUnderline" v-on:mouseleave="removeUnderline">
                    <div class="cube">
                        <div class="face front">
                            소장품
                        </div>
                        <div class="face back">
                            Collection
                        </div>
                    </div>
                    <Transition name="menu-fade" class="transition">
                        <div v-if="expandMenu" >
                            <div style="height: 58px"/>
                            <li class="sub-menu" v-for="(item, index) in menuList4">
                                <div class="sub-menu-item cube" v-on:click="setSubPageScreen">
                                    <div class="face front">
                                        {{ item.kor }}
                                    </div>
                                    <div class="face back" style="top: 8px;">
                                        {{ item.eng }}
                                    </div>
                                </div>
                            </li>
                        </div>
                    </Transition>
                </div>
                <div class="menu" style="width: 155px" v-on:mouseover="showUnderline" v-on:mouseleave="removeUnderline">
                    <div class="cube">
                        <div class="face front">
                            미술연구
                        </div>
                        <div class="face back">
                            Art Research
                        </div>
                    </div>
                    <Transition name="menu-fade" class="transition">
                        <div v-if="expandMenu" >
                            <div style="height: 58px"/>
                            <li class="sub-menu" v-for="(item, index) in menuList5">
                                <div class="sub-menu-item cube" v-on:click="setSubPageScreen">
                                    <div class="face front">
                                        {{ item.kor }}
                                    </div>
                                    <div class="face back" style="top: 8px;">
                                        {{ item.eng }}
                                    </div>
                                </div>
                            </li>
                        </div>
                    </Transition>
                </div>
            </div>
            <div class="hover-underline" 
                    :style="{transform: 'translateX(' +underlineXOffset + 'px)', opacity: opacity }"/>    
        </div>
        <div class="menu-items">
            <div style="width: 118px"/>
            <div class="search-box">
                <img class="search-icon" :src="icon">
            </div>
            <div style="width: 26px"/>
            <div class="reserve-button">
                전시 관람 예약하기
            </div>
            <div style="width: 17px"/>
            <div style="font-size: 17px; font-weight: 600;">
                KO / 한국어
            </div>
            <div style="width: 8px"/>
            <img :src="down">
        </div>
    </div>
    
</template>
<script>
import { ref } from 'vue'
import headerLogo from '@/assets/header_logo.png'
import searchIcon from '@/assets/search_icon.png'
import chevronDown from '@/assets/chevron-down.png'

export default {
    props: [
        "currentPage"
    ],
    data() {
        return {
            underlineXOffset: null,
            opacity: 0,
            expandMenu: false,
            menuList1: [
                {
                    kor: "서울",
                    eng: "seoul"
                },
                {
                    kor: "과천",
                    eng: "Gwacheon"
                },
                {
                    kor: "덕수궁",
                    eng: "Deoksugun"
                },
                {
                    kor: "청주",
                    eng: "Cheongju"
                },
                {
                    kor: "디지털미술관",
                    eng: "Digital Museum"
                }
            ],
            menuList2: [
                {
                    kor: "현재 전시",
                    eng: "Current Exhibition"
                },
                {
                    kor: "예정 전시",
                    eng: "Scheduled Exhibition"
                },
                {
                    kor: "과거 전시",
                    eng: "Past Exhibition"
                },
                {
                    kor: "전시 해설",
                    eng: "Commentary"
                }
            ],
            menuList3: [
                {
                    kor: "어린이",
                    eng: "Children"
                },
                {
                    kor: "청소년",
                    eng: "Adolescent"
                },
                {
                    kor: "성인",
                    eng: "Adult"
                },
                {
                    kor: "교사",
                    eng: "Teacher"
                },
                {
                    kor: "교육자료실",
                    eng: "Library"
                }
            ],
            menuList4: [
                {
                    kor: "소장품 검색",
                    eng: "Search"
                },
                {
                    kor: "보존과학",
                    eng: "Conversation"
                }
            ],
            menuList5: [
                {
                    kor: "도서와 아카이브",
                    eng: "Books / Archives"
                },
                {
                    kor: "연구 및 발간 자료",
                    eng: "Research/Publication"
                },
                {
                    kor: "MMCA 리서치랩",
                    eng: "MMCA Research Lab"
                },
                {
                    kor: "레지던시",
                    eng: "Residency"
                },
                {
                    kor: "미술은행",
                    eng: 'Art bank'
                }
            ]
        }
    },
    methods: {
        showMenu() {
            if (!this.expandMenu) {
                this.expandMenu = true
            }
        },
        removeMenu() {
            this.expandMenu = false
        },
        showUnderline(event) {
            const x = event.currentTarget.offsetLeft
            const width = event.currentTarget.getBoundingClientRect().width
            const center = x + width / 2 - 33.5
            if (this.underlineXOffset !== center) {
                this.underlineXOffset = center
            }
            if (this.opacity !== 1) {
                this.opacity = 1
            }
        },
        removeUnderline(event) {
            this.opacity = 0
        }
    },
    setup() {
        const logo = ref(headerLogo)
        const icon = ref(searchIcon)
        const down = ref(chevronDown)
        return {
            logo,
            icon,
            down,
        }
    }
}
</script>

<style>
    a {
        text-decoration: none;
    }
    img {
        object-fit: contain;
    }
    .header {
        z-index: 899;
        display: flex;
        position: fixed;
        top: 0;
        width: 100%;
        padding-top: 24px;
        align-items: flex-start;
        white-space: nowrap;
        padding-bottom: 32px;
        background-color: white;
    }
    .header .menu-bar {
        position: relative;
        z-index: 998;
    }
    .header .menu {
        font-size: 18px;
        font-weight: 500;
        padding-top: 24px;
        padding-bottom: 12px;
        display: flex;
        flex-direction: column;
        align-items: center;
        cursor: pointer;
    }
    .header .menu-list {
        display: flex;
        float: left;
    }
    .header .menu-bar .menu-list .menu .transition {
        width: 100%;
    }
    .header .sub-menu {
        list-style-type: none;
        display: flex;
        justify-content: center;
        width: 100%;
    }
    
    .header .sub-menu-item {
        cursor: pointer;
        font-size: 16px;
        font-weight: 500;
        width: 100%;
        padding: 8px 0;
        color: #7f7f7f;
    }
    .cube {
        width: 100%;
        position: relative;
        transform: translateZ(100px);
        backface-visibility: hidden;
        perspective: 200px;
    }
    .face {
        width: 100%;
        background-color: white;
        text-align: center;
        z-index: -1;
    }
    .front {
        transform: rotateX(0deg);
        transition: transform 0.3s;
        backface-visibility: hidden;
        transform-style: preserve-3d;
    }
    .back {
        transform: rotateX(180deg);
        position: absolute;
        left: 0;
        top: 0px;
        z-index: -1;
        transition: transform 0.3s;
        transform-style: preserve-3d;
    }
    .cube:hover .front {
        transform: rotateX(180deg);
    }
    .cube:hover .back {
        transform: rotateX(0deg);
    }
    .header .sub-menu-item:hover {
        color: black;
    }
    .header .hover-underline {
        position: absolute;
        background-color: #998a5f;
        height: 2px;
        width: 67px;
        top: 56px;
        z-index: -1;
        transition: all 0.3s ease;
    }
    .header .menu-items {
        display: flex;
        flex-direction: row;
        padding-top: 8px;
        align-items: center;
    }
    .header .search-box {
        border-width: 2px;
        border-style: solid;
        border-color: rgb(127, 127, 127);
        border-radius: 21.5px;
        width: 311px;
        height: 43px;
        padding-right: 19px;
        display: flex;
        justify-content: flex-end;
        align-items: center;
    }
    .header .search-icon {
        width: 18px;
        height: 18px;
    }
    .header .reserve-button {
        width: 176px;
        height: 47px;
        font-size: 16px;
        font-weight: 500;
        background-color: black;
        color: white;
        border-radius: 23.5px;
        display: flex;
        cursor: pointer;
        align-items: center;
        justify-content: center;
    }
    .header .language-button {
        font-size: 17px;
        font-weight: 600;
    }

    .header .menu-fade-enter-active,
    .header .menu-fade-leave-active {
        transition: opacity 0.3s ease;
    }
    .header .menu-fade-enter-from,
    .header .menu-fade-leave-to {
        opacity: 0;
    }
</style>