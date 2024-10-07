<template>
    <div class="search-button">
        <div style="height: 30px"/>
        <div style="font-size: 16; color: white; font-weight: 500;">
            스마트 검색
        </div>
        <div style="height: 14px;"/>
        <img :src="icon">
    </div>
</template>
<script>
import { ref } from 'vue'
import searchIconWhite from '@/assets/search_icon_white.png'

export default {
    setup() {
        const icon = ref(searchIconWhite)
        return {
            icon
        }
    }
}
</script>
<style>
    .search-button {
        position: fixed;
        bottom: 99px;
        right: 99px;
        width: 99px;
        height: 99px;
        background-color: black;
        border-radius: 100px;
        display: flex;
        align-items: center;
        flex-direction: column;
    }
</style>