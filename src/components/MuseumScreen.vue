<template>
    <div class="museum-screen">
        <div class="museum-screen-title">
            국립현대미술관
        </div>
        <div style="height: 40px"/>
        <div class="museum-list">
            <li class="museum-list-item" v-for="item of museums">
                <div style="position: relative">
                    <div class="museum-item-mouseover">
                        <div style="height: 118px"/>
                        <div class="museum-item-mouseover-title">
                            {{ item.location + "관" }}
                        </div>
                        <div style="height: 5px"/>
                        <div class="divider"/>
                        <div style="height: 22px"/>
                        <div class="museum-item-mouseover-seeall">
                            전체 일정 보기
                            <span class="material-icons display-all-chevron">chevron_right</span>
                        </div>
                    </div>
                    <div class="museum-image-container">
                        <img class="museum-item-image" :src="item.image">
                    </div>
                    
                </div>
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
    .museum-item-mouseover {
        position: absolute;
        top: 0;
        width: 100%;
        height: 100%;
        opacity: 0;
        background-color: rgba(0, 0, 0, 0.3);
        border-radius: 16px;
        z-index: 100;
        transition: all 0.3s ease;
        color: white;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .museum-item-mouseover .divider {
        background-color: white; 
        width: 0px; 
        height: 1px;
        transition: width 1s ease;
    }
    .museum-item-mouseover:hover {
        opacity: 1;
    }
    .museum-item-mouseover:hover >.divider {
        width: 100px;
    }
    .museum-item-mouseover:hover ~.museum-image-container .museum-item-image {
        transform: scale(1.2);
    }
    .museum-image-container {
        width: 377px;
        height: 772px;
        overflow: hidden;
        overflow-y: hidden;
        border-radius: 16px;
    }
    .museum-item-image {
        opacity: 1;
        display: block;
        transition: transform 1s ease;
        
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
    .museum-item-mouseover-title {
        font-size: 37px;
        font-weight: 600;
    }
    .museum-item-mouseover-seeall {
        display: flex;
        font-size: 20px;
        font-weight: 600;
    }
</style>