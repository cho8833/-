
<template>
    <Transition name="fade">
        <div class="splash-screen" v-if="showSplashScreen">
            <Transition appear name="fade" @after-enter="dismissFirstLogo" @after-leave="showSecond">
                <div v-if="showFirstLogo">
                    <img :src="firstLogo">
                </div>
            </Transition>
            <Transition name="fade" @after-enter="dismissSplash">
                <div v-if="showSecondLogo">
                    <img :src="secondLogo">
                </div>
            </Transition>
        </div>
    </Transition>

    <MainScreen/>
</template>

<script>
import { ref } from 'vue'
import splash1 from '@/assets/splash1.png'
import splash2 from '@/assets/splash2.png'
import MainScreen from './MainScreen.vue';

export default {
    components: {
        MainScreen
    },
    data() {
        return {
            showFirstLogo: true,
            showSecondLogo: false,
            showSplashScreen: true,
        }
    },
    methods: {
        dismissFirstLogo() {
            this.showFirstLogo = false
        },
        showSecond() {
            this.showSecondLogo = true
        },
        dismissSplash() {
            this.showSecondLogo = false
            this.showSplashScreen = false
        },
    },
    setup() {
        const firstLogo = ref(splash1)
        const secondLogo = ref(splash2)
        return {
            firstLogo,
            secondLogo
        }
    },
}
</script>

<style>
    .splash-screen {
        background-color: white;
        position: absolute;
        top: 0;
        z-index: 999;
        left: 0;
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .fade-enter-active,
    .fade-leave-active {
        transition: opacity 1s ease;
    }

    .fade-enter-from,
    .fade-leave-to {
        opacity: 0;
    }
</style>