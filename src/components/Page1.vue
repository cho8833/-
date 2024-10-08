<template>
    <div class="page1">
        <div class="introduce">
            <div class="title">
                문경원+전준호, 자유의 마을
            </div>
            <div class="discription">
                <div class="discription-date">
                    한국 실험미술 1960-70년대
                </div>
                <div style="height: 8px"/>
                <div style="color: #838080">
                    미국 LA 해머미술관 02.11 - 05.12
                </div>
            </div>
        </div>
        <div style="height: 32px;"/>
        <img :src="mainPhoto">
    </div>
</template>
<script>
import { ref } from 'vue';
import photo from '@/assets/main_photo.png'

export default {
    setup() {
        const mainPhoto = ref(photo)
        return {
            mainPhoto
        }
    }
}
</script>
<style>
    .page1 {
        padding-top: 157px;
        width: 1592px;
    }
    .introduce {
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
        padding-top: 74px;
        padding-left: 149px;
    }
    .title {
        font-size: 80px;
        font-weight: 700;
    }
    .discription {
        font-size: 20px;
        font-weight: 500;
    }

</style>