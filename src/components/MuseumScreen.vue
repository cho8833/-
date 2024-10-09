<template>
    <div class="museum-screen">
        <div class="museum-screen-title">
            국립현대미술관
        </div>
        <div style="height: 40px"/>
        <div class="museum-list">
            <li class="museum-list-item" v-for="item of museums">
                <img :src="item.image">
                <div style="height: 20px"/>
                <div class="museum-list-item-title">
                    {{ item.location }}
                </div>
                <div style="height: 12px"/>
                <div class="museum-list-item-description" v-html="item.description">
                </div>
            </li>
        </div>
    </div>
</template>

<script>
import seoul from '@/assets/seoul.png'
import gwacheon from '@/assets/gwacheon.png'
import cheongjoo from '@/assets/cheongjoo.png'
import deoksoogoong from '@/assets/deoksoogoong.png'

export default {
    data() {
        const museums = [
            {
                location: "서울",
                description: "월, 화, 목, 금, 일요일 10:00-18:00<br/>수, 토요일 야간개장 10:00-21:00",
                image: seoul
            },
            {
                location: "과천",
                description: "화요일~일요일 10:00-18:00<br/>월요일 휴관",
                image: gwacheon
            },
            {
                location: "덕수궁",
                description: "화, 목, 금, 일요일 10:00-18:00<br/>수, 토요일 야간개장 10:00-21:00<br/>월요일 휴관",
                image: deoksoogoong
            },
            {
                location: "청주",
                description: "화요일~일요일 10:00-18:00<br/>월요일 휴관",
                image: cheongjoo
            }
        ]
        return {
            museums
        }
    }
}
</script>

<style>

    .museum-screen {
        padding-left: 149px;
    }
    .museum-screen-title {
        font-size: 35px;
        font-weight: 700;
    }
    .museum-list {
        display: flex;
    }
    .museum-list-item {
        list-style-type: none;
        padding-right: 35px;
    }
    .museum-list-item-title {
        font-size: 23px;
        font-weight: 600;
    }
    .museum-list-item-description {
        font-size: 16px;
        font-weight: 500;
        color: #a7a9ac;
    }
</style>