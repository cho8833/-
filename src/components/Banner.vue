<template>
    <div class="banner">
        <img :src="banner">
        <div class="banner-title-box">
            <div style="height: 82px"/>
            <div class="banner-title-1">
                MMCA Research Lab
            </div>
            <div style="height: 18px"/>
            <div class="banner-title-2">
                한국미술 연구 온라인 플랫폼
            </div>
            <div style="height: 22px"/>
            <div class="banner-title-3">
                Online Platform for Korean Art Research
            </div>
        </div>
    </div>
</template>

<script setup>
    import banner from '@/assets/banner.png'
</script>

<style>
    .banner {
        position: relative;
        height: 278px;
    }
    .banner-title-box {
        position: absolute;
        padding-left: 151px;
        height: 100%;
        top: 0;
        color: #fcf6e4;
        line-height: 1;
    }
    .banner-title-1 {
        font-size: 30px;
        font-weight: 600;
    }
    .banner-title-2 {
        font-size: 40px;
        font-weight: 600;
    }
    .banner-title-3 {
        font-size: 18px;
        font-weight: 300;
    }
</style>