<template>
    <div class="header">
        <div width="91px"/>
        <img :src="logo">
        <div width="96px"/>
        <div>
            관람ㆍ참여
        </div>
    </div>
    
</template>

<script>
import { ref } from 'vue'
import headerLogo from '@/assets/header_logo.png'

export default {
    setup() {
        const logo = ref(headerLogo)

        return {
            logo
        }
    }
}
</script>

<style>
    .header {
        display: flex;
        float: left;
        background-color: white;
        position: absolute;
        top: 0;
        z-index: 998;
        padding-top: 24px;
    }
</style>