<template>
    <div class="header" v-on:mouseover="appearHeader" v-on:mouseleave="transparentHeader" :style="{backgroundColor: isHeaderHover ? 'white' : 'transparent'}">
        <div style="width: 91px;"/>
        <img :src="logo">
        <div style="width: 56px"/>
        <div class="menu-bar">
            <div class="menu-list" v-on:mouseover="showUnderline" v-on:mouseleave="removeUnderline">
                <div class="menu" style="width: 154px;">
                    관람ㆍ참여
                    <Transition name="menu-fade">
                        <div v-if="expandMenu" >
                            <div style="height: 58px"/>
                            <li class="sub-menu" v-for="(item, index) in menuList1">
                                <div class="sub-menu-item">
                                    {{ item }}
                                </div>
                            </li>
                        </div>
                    </Transition>
                </div>
                <div class="menu" style="width: 106px">
                    전시
                    <Transition name="menu-fade">
                        <div v-if="expandMenu" >
                            <div style="height: 58px"/>
                            <li class="sub-menu" v-for="(item, index) in menuList2">
                                <div class="sub-menu-item">
                                    {{ item }}
                                </div>
                            </li>
                        </div>
                    </Transition>
                </div>
                <div class="menu" style="width:115px">
                    교육
                    <Transition name="menu-fade">
                        <div v-if="expandMenu" >
                            <div style="height: 58px"/>
                            <li class="sub-menu" v-for="(item, index) in menuList3">
                                <div class="sub-menu-item">
                                    {{ item }}
                                </div>
                            </li>
                        </div>
                    </Transition>
                </div>
                <div class="menu" style="width:116px">
                    소장품
                    <Transition name="menu-fade">
                        <div v-if="expandMenu" >
                            <div style="height: 58px"/>
                            <li class="sub-menu" v-for="(item, index) in menuList4">
                                <div class="sub-menu-item">
                                    {{ item }}
                                </div>
                            </li>
                        </div>
                    </Transition>
                </div>
                <div class="menu" style="width: 147px">
                    미술연구
                    <Transition name="menu-fade">
                        <div v-if="expandMenu" >
                            <div style="height: 58px"/>
                            <li class="sub-menu" v-for="(item, index) in menuList5">
                                <div class="sub-menu-item">
                                    {{ item }}
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
            <div style="width: 151px"/>
        </div>
    </div>
    
</template>

<script>
import { ref } from 'vue'
import headerLogo from '@/assets/header_logo.png'
import searchIcon from '@/assets/search_icon.png'
import chevronDown from '@/assets/chevron-down.png'

export default {
    data() {
        return {
            underlineXOffset: null,
            isHeaderHover: false,
            opacity: 0,
            expandMenu: false,
            menuList1: [
                '서울', '과천', '덕수궁', '청주', '디지털미술관'
            ],
            menuList2: [
                '현재 전시', '예정 전시', '과거 전시', '전시 해설'
            ],
            menuList3: [
                '어린이', '청소년', '성인', '교사', '교육자료실'
            ],
            menuList4: [
                '소장품 검색', '보존과학'
            ],
            menuList5: [
                '도서와 아카이브', '연구 및 발간 자료', 'MMCA 리서치랩', '레지던시', '미술은행'
            ]
        }
    },
    methods: {
        appearHeader() {
            this.isHeaderHover = true
        },
        transparentHeader() {
            this.isHeaderHover = false
        },
        showUnderline(event) {
            const x = event.srcElement.offsetLeft
            const width = event.srcElement.getBoundingClientRect().width
            const center = x + width / 2 - 33.5

            if (this.underlineXOffset !== center) {
                this.underlineXOffset = center
            }
            if (this.opacity !== 1) {
                this.opacity = 1
            }
            if (!this.expandMenu) {
                this.expandMenu = true
            }
        },
        removeUnderline(event) {
            this.menuhover = false;
            this.opacity = 0
            this.expandMenu = false
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
    img {
        object-fit: contain;
    }
    .header {
        z-index: 899;
        display: flex;
        position: fixed;
        top: 0;
        padding-top: 24px;
        align-items: flex-start;
        white-space: nowrap;
        padding-bottom: 32px;
        transition: background-color 0.3s ease;
    }
    .menu-bar {
        position: relative;
        z-index: 998;
    }
    .menu {
        font-size: 18px;
        font-weight: 500;
        padding-top: 24px;
        padding-bottom: 12px;
        display: flex;
        flex-direction: column;
        align-items: center;
        cursor: pointer;
    }
    .menu-list {
        display: flex;
        float: left;
    }
    .sub-menu {
        list-style-type: none;
        display: flex;
        justify-content: center;
    }
    .sub-menu-item {
        cursor: pointer;
        font-size: 16px;
        font-weight: 500;
        margin-bottom: 15px;
        color: #7f7f7f;
    }
    .sub-menu-item:hover {
        color: black;
    }
    .hover-underline {
        position: absolute;
        background-color: #998a5f;
        height: 2px;
        width: 67px;
        top: 56px;
        z-index: -1;
        transition: all 0.3s ease;
    }
    .menu-items {
        display: flex;
        flex-direction: row;
        padding-top: 8px;
        align-items: center;
    }
    .search-box {
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
    .search-icon {
        width: 18px;
        height: 18px;
    }
    .reserve-button {
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
    .language-button {
        font-size: 17px;
        font-weight: 600;
    }

    .menu-fade-enter-active,
    .menu-fade-leave-active {
        transition: opacity 0.3s ease;
    }
    .menu-fade-enter-from,
    .menu-fade-leave-to {
        opacity: 0;
    }
</style>