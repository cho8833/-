<template>
    <div class="collection-screen">
        <div class="title">
            국립현대미술관 소장품
        </div>
        <div style="height: 31px"/>
        <div class="description">
            시대별 회화, 판화, 조각 및 설치, 공예, 건축 등
        </div>
        <div class="description">
            국립현대미술관이 소장하고 있는 다양한 작품을 만나보세요.
        </div>
        <div style="height: 85px"/>
        <div class="collection-list">
            <li class="collection-item" v-for="item of collections">
                <div style="width: 35px;"/>
                <div style="position: relative; width: 340px; height: 468px;">
                    <img :src="item.image">
                    <div class="title">
                        {{ item.title }}
                    </div>
                    <div class="chevron-button">
                        <span class="material-icons chevron">chevron_right</span>
                    </div>
                </div>
            </li>
        </div>
    </div>
</template>

<script>
import collection1 from '@/assets/collection1.png'
import collection2 from '@/assets/collection2.png'
import collection3 from '@/assets/collection3.png'
import collection4 from '@/assets/collection4.png'

export default {
    data() {
        const collections = [
            {
                image: collection1,
                title: '이건희 컬렉션'
            },
            {
                image: collection2,
                title: '1910~1920년대'
            },
            {
                image: collection3,
                title: '1930~1940년대'
            },
            {
                image: collection4,
                title: '1950~1960년대'
            }
        ]
        return {
            collections
        }
    }
}
</script>

<style>
    .collection-screen {
        padding-left: 150px;
        padding-right: 150px;
    }
    .collection-screen .title {
        font-size: 35px;
        font-weight: 700;
    }
    .collection-screen .description {
        color: #646157;
        font-size: 20px;
        font-weight: 400;
    }
    .collection-screen .collection-list {
        display: flex;
        justify-content: flex-end;
    }
    .collection-screen .collection-list .collection-item {
        list-style-type: none;
        display: flex;
    }
    .collection-screen .collection-list .collection-item .chevron-button {
        position: absolute;
        bottom: 0;
        right: 0;
        width: 80px;
        height: 80px;
        background-color: black;
        display: flex;
        
        align-items: center;
        justify-content: center;
    }
    .collection-screen .collection-list .collection-item .title {
        font-size: 20px;
        font-weight: 600;
        color: white;
        position: absolute;
        bottom: 29px;
        left: 24px;
    }
    .collection-screen .collection-list .collection-item .chevron-button .chevron {
        color: white;
        font-size: 40px;
    }
</style>