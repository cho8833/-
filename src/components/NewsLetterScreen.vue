<template>
    <div class="news-letter-screen">
        <div class="title">
            MMCA 뉴스레터
        </div>
        <div class="navigation">
            <span class="material-icons chevron chevron-left">chevron_left</span>
            <div style="display: flex; width: 37px; justify-content: space-between;">
                <div class="current-page">1</div>
                <div class="total-page">/</div>
                <div class="total-page">3</div>
            </div>
            <span class="material-icons chevron">chevron_right</span>
        </div>
        <div style="height: 34px"/>
        <div class="news-letter-list">
            <li class="news-letter-item" v-for="item of newsLetters">
                <div class="description-section">
                    <div style="height: 24px;"/>
                    <div class="title" v-html="item.title"/>
                    <div style="height: 35px;"/>
                    <div style="display: flex; align-items: center;">
                        <div class="tag">
                            {{  item.tag  }}
                        </div>
                        <div style="width: 11px"/>
                        <div class="text">
                            {{ item.date }}
                        </div>
                        <div style="width: 10px;"/>
                        <div class="divider"/>
                        <div style="width: 11px"/>
                        <span class="material-symbols-outlined icon">visibility</span>
                        <div style="width: 13px;"/>
                        <div class="text">
                            {{ item.view }}
                        </div>
                        <div style="width: 16px;"/>
                        <div class="material-symbols-outlined icon">share</div>
                        <div style="width: 16px"/>
                        <div class="material-symbols-outlined icon">favorite</div>
                    </div>
                </div>
                <img class="image" :src="item.image">
            </li>
        </div>
        <div style="height: 76px"/>
        <div class="subscribe-button">
            뉴스레터 구독하기
        </div>
        <div style="height: 70px"/>
    </div>
</template>
<script>
import newsLetter1 from '@/assets/news_letter1.png'
import newsLetter2 from '@/assets/news_letter2.png'
import newsLetter3 from '@/assets/news_letter3.png'
import newsLetter4 from '@/assets/news_letter4.png'

export default {
    data() {
        const newsLetters = [
            {
                title: "키워드로 만나는 2024 국립현대미술관",
                image: newsLetter1,
                tag: "포커스",
                date: "2024-03-15",
                view: 619
            },
            {
                title: "«올해의 작가상 2023» 권병준 작가<br> 최종 수상!",
                image: newsLetter2,
                tag: "미술관 플러스",
                date: "2024-02-15",
                view: 1400
            },
            {
                title: "모든 것은 새벽의 빛깔을 지닌다,<br/>권옥연 ‹상형(象形)›",
                image: newsLetter3,
                tag: "소장품 더보기",
                date: "2024-02-15",
                view: 1189
            },
            {
                title: "국립현대미술관 2024년 전시 계획 공개",
                image: newsLetter4,
                tag: "포커스",
                date: "2024-01-15",
                view: 5353
            }
        ]
        return {
            newsLetters
        }
    }
}
</script>
<style>
    .news-letter-screen {
        display: flex;
        flex-direction: column;
        background-color: #f5f3ec;
        padding-top: 117px;
        padding-left: 146px;
        padding-right: 152px;
    }
    .news-letter-screen .title {
        font-size: 35px;
        font-weight: 700;
        color: black;
    }
    .news-letter-screen .navigation {
        align-self: end;
        display: flex;
        font-size: 20px;
        font-weight: 700;
        text-align: center;
    }
    .news-letter-screen .navigation .chevron-left {
        color: #babab8;
    }
    .news-letter-screen .navigation .current-page {
        color: #a8996e;
    }
    .news-letter-screen .navigation .total-page {
        color: #babab8;
    }
    .news-letter-screen .news-letter-list {
        display: grid;
        row-gap: 46px;
        column-gap: 46px;
        grid-template-columns: repeat(2, auto);
        list-style-type: none;
    }
    .news-letter-screen .news-letter-list .news-letter-item {
        background-color: #e9e7e1;
        display: flex;
        justify-content: space-between;
        border-radius: 16px;
        width: 787px;
        height: 277px;
        padding: 34px 45px;
    }
    .news-letter-screen .news-letter-list .news-letter-item .image {
        border-radius: 12px;
    }
    .news-letter-screen .news-letter-list .news-letter-item .description-section .title {
        font-size: 28px;
        font-weight: 700;
        color: black;
        line-height: 40px;
    }
    .news-letter-screen .news-letter-list .news-letter-item .description-section .tag {
        border-radius: 15px;
        background-color: #e3ded3;
        padding: 7px 12px;
        color: #928770;
    }
    .news-letter-screen .news-letter-list .news-letter-item .description-section .text {
        font-size: 18px;
        font-weight: 600;
        color: #545454;
    }
    .news-letter-screen .news-letter-list .news-letter-item .description-section .divider {
        width: 2px;
        height: 20px;
        background-color: #d4d1c9;
    }
    .news-letter-screen .news-letter-list .news-letter-item .description-section .icon {
        color: #88857f;
    }
    .news-letter-screen .subscribe-button {
        align-self: center;
        width: 201px;
        height: 54px;
        display: flex;
        align-items: center;
        padding: 19px 38px;
        background-color: black;
        color: white;
        font-size: 18px;
        font-weight: 500;
        white-space: nowrap;
        border-radius: 27px;
    }

</style>