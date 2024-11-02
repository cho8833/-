<template>
    <div class="footer">
        <div class="description-section">
            <img :src="logo">
            <div style="width: 223px"/>
            <div class="location-box">
                <div class="header-title">
                    국립현대미술관 위치
                </div>
                <div style="height: 33px;"/>
                <li class="location-item" v-for="item of museums">
                        <div class="name">
                            {{ item.name }}
                        </div>
                        <div class="address">
                            {{  item.address  }}
                        </div>
                </li>
            </div>
            <div style="width: 145px"/>
            <div class="phone-box">
                <div class="header-title">
                    대표전화
                </div>
                <div style="height: 33px"/>
                <li class="phone-item" v-for="item of museums">
                    <div class="name">
                        {{ item.name }}
                    </div>
                    <div class="number">
                        {{ item.number }}
                    </div>
                </li>
            </div>
            <div style="width: 432px"/>
            <div class="hyperlink-section">
                <div style="display:flex">
                    <img :src="instaIcon">
                    <div style="width: 16px"/>
                    <img :src="faceIcon">
                    <div style="width: 16px"/>
                    <img :src="youIcon">
                </div>
                <div style="height: 31px"/>
                <li class="hyperlink" v-for="hyperlink of hyperlinks">
                    {{ hyperlink }}
                    <div style="height: 12px"/>
                </li>
            </div>
        </div>
        <div style="height: 88px"/>
        <div class="divider"/>
        <div style="height: 46px"/>
        <div class="menu-box">
            <div class="first-title">
                개인정보처리방침
            </div>
            <div class="divider"/>
            <div class="menu-title">
                이용약관
            </div>
            <div class="divider"/>
            <div class="menu-title">
                저작권정책
            </div>
            <div class="divider"/>
            <div class="menu-title">
                국민신문고
            </div>
            <div class="divider"/>
            <div class="menu-title">
                정보공개
            </div>
            <div class="divider"/>
            <div class="menu-title">
                클린신고센터
            </div>
        </div>
        <div style="height: 80px"/>
    </div>
</template>

<script>
import footerLogo from '@/assets/footer_logo.png'
import instagramIcon from '@/assets/instagram_icon_outlined.png'
import facebookIcon from '@/assets/facebook_icon.png'
import youtubeIcon from '@/assets/youtube_icon.png'
import { ref } from 'vue'

export default {
    data() {
        const museums = [
            {
                name: "서울",
                address: "서울특별시 종로구 삼청로 30",
                number: "02-3701-9500"
            },
            {
                name: "과천",
                address: "경기도 과천시 광명로 313",
                number: "02-2188-6000"
            },
            {
                name: "덕수궁",
                address: "서울특별시 중구 세종대로 99",
                number: "02-2022-0600"
            },
            {
                name: "청주",
                address: "충청북도 청주시 상당구 상당로 314",
                number: "043-261-1400"
            }
        ]
        const hyperlinks = [
            "미술관 소개",
            "새소식",
            "자주 묻는 질문",
            "사이트맵",
            "국립현대미술관 문화재단",
            "멤버십",
            "온라인숍"
        ]
        return {
            museums,
            hyperlinks
        }
    },
    setup() {
        const logo = ref(footerLogo)
        const instaIcon = ref(instagramIcon)
        const youIcon = ref(youtubeIcon)
        const faceIcon = ref(facebookIcon)
        return {
            logo,
            instaIcon,
            youIcon,
            faceIcon
        }
    }
}
</script>

<style>
    .footer {
        background-color: black;
        width: 100%;
        padding-top: 81px;
        padding-left: 152px;
        display: flex;
        flex-direction: column;

    }
    .footer .description-section {
        display: flex;
        align-items: flex-start;
    }

    .footer .description-section .location-box .header-title {
        font-size: 16px;
        font-weight: 700;
        color: #fefefe;
    }
    .footer .description-section .location-box .location-item {
        display: flex;
        margin-bottom: 18px;
    }
    .footer .description-section .location-box .location-item .name {
        color: #b7b5b5;
        width: 50px;
        font-weight: 300;
        font-size: 15px;
    }
    .footer .description-section .location-box .location-item .address {
        color: #706d6d;
        font-weight: 300;
        font-size: 15px;
    }
    .footer .description-section .phone-box .header-title {
        color: #fefefe;
        font-weight: 700;
        font-size: 16px;
    }
    .footer .description-section .phone-box .phone-item {
        display: flex;
        margin-bottom: 18px;
    }
    .footer .description-section .phone-box .phone-item .name {
        color: #b7b5b5;
        width: 50px;
        font-weight: 300;
        font-size: 15px;
    }
    .footer .description-section .phone-box .phone-item .number {
        color: #706d6d;
        font-weight: 300;
        font-size: 15px;
    }
    .footer .description-section .hyperlink-section .hyperlink {
        color: #c9c7c7;
        font-size: 15px;
        font-weight: 600;
        list-style-type: none;
    }
    
    .footer .divider {
        width: 1185px;
        height: 1px;
        background-color: #706d6d;
        align-self: center;
    }
    .footer .menu-box {
        align-self: center;
        display: flex;
        width: 1185px;
    }
    .footer .menu-box .first-title {
        font-weight: 400;
        font-size: 17px;
        color: white;
        margin-right: 20px;
    }
    .footer .menu-box .menu-title {
        font-weight: 300;
        font-size: 17px;
        color: #706d6d;
        margin-right: 20px;
    }
    .footer .menu-box .divider {
        height: 18px;
        width: 1px;
        background-color: #706d6d;
        margin-right: 20px;
    }
</style>