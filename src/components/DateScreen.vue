<template>
    <div class="date-screen">
            <div class="date-title">
                국립현대미술관 일정
            </div>
            <div style="height: 26px"/>
            <div class="all-event-box">
                <div class="all-event">
                    전체 일정 보기
                </div>
                <div style="width: 10px"/>
                <img :src="rightIcon">
            </div>
        <div style="height: 51px"/>
        <div class="date-container">
            <div class="scroll-button scroll-button-left" @click="onDateFocusChange(true)">
                <span class="material-icons scroll-chevron">chevron_left</span>
            </div>
            <div class="scroll-button scroll-button-right" @click="onDateFocusChange(false)">
                <span class="material-icons scroll-chevron">chevron_right</span>
            </div>
            <div class="date-box">
                <li class="date-item" v-for="(item, index) in dates">
                    <div class="date-text-box" :ref="'date-box-'+index" :class="selectedDateIndex === index ? selectedDateBoxClass : ''"  @click="onDateClick(index, $event)">
                        <div class="text-date">
                            {{ item.getDate() }}
                        </div>
                        <div style="height: 14px"/>
                        <div class="text-day">
                            {{ days[item.getDay()] + "요일" }}
                        </div>
                    </div>
                </li>
            </div>
        </div>
    </div>
</template>

<script>
import chevronRight from '@/assets/chevron-right.png'
import { ref } from 'vue'

function getDates(today) {
    const startDate = new Date(today.setDate(today.getDate() - 15))
    const endDate = new Date(today.setDate(today.getDate() + 30))
    var dateArray = new Array();
    var currentDate = new Date(startDate);
    while (currentDate <= endDate) {
        dateArray.push(new Date(currentDate))
        currentDate.setDate(currentDate.getDate() + 1)
    }
    return dateArray;
}
function getSameDayIndex(date, dates) {
    const found = dates.findIndex((element) => element.getDate() === date.getDate()
        && element.getMonth() === date.getMonth() && element.getYear() === date.getYear())
    return found
}

export default {
    data() {
        const days = ["일", "월", "화", "수", "목", "금", "토"];
        return {
            days
        }
    },
    setup() {
        const rightIcon = ref(chevronRight)
        const dates = ref(getDates(new Date()))
        const today = new Date()
        const selectedDateIndex = ref(getSameDayIndex(today, dates.value))
        const selectedDateBoxClass = ref('date-text-box-selected')
        const focusDateIndex = ref(selectedDateIndex.value)
        
        return {
            rightIcon,
            dates,
            selectedDateIndex,
            selectedDateBoxClass,
            focusDateIndex
        }
    },
    methods: {
        onDateClick(index, event) {
            this.selectedDateIndex = index
            this.focusDateIndex = index
            event.target.scrollIntoView({behavior: "smooth", inline: "center", block: "nearest"})
        },
        onDateFocusChange(isLeft) {
            this.focusDateIndex += isLeft ? -7 : 7;
            const focusBox = this.$refs['date-box-' + this.focusDateIndex][0]
            focusBox.scrollIntoView({behavior: "smooth", inline: "center", block: "nearest"})
        }
    },
    mounted() {
        const todayBox = this.$refs['date-box-' + this.selectedDateIndex][0]
        todayBox.scrollIntoView({inline: "center", block: "nearest"})
    }

}
</script>

<style>
    .date-screen {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .date-title {
        font-size: 35px;
        font-weight: 700;
    }
    .all-event-box {
        display: flex;
    }
    .all-event {
        font-size: 20px;
        font-weight: 600;
        color: #838080;
    }
    .date-box {
        width: 1600px;
        white-space: nowrap;
        overflow-x: auto;
    }
    .date-item {
        list-style-type: none;
        display: inline-block;
        width: 226px;
        height: 253px;
        border-color: #e8e7e6;
        border-top-width: 4px;
        border-bottom-width: 4px;
        border-left-width: 2px;
        border-right-width: 2px;
        border-style: solid;
    }
    .date-text-box {
        width: 100%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        color: #babab8;
        cursor: pointer;
        background-color: white;
        transition: all 0.3s ease;
    }
    .date-text-box-selected,
    .date-text-box:hover {
        background-color: black;
        color: white;
    }
    .text-date {
        font-size: 70px;
        font-weight: 400;
    }
    .text-day {
        font-size: 16px;
        font-weight: 500;
    }
    .date-container {
        position: relative;
    }
    .scroll-button {
        width: 55px;
        height: 55px;
        background-color: #e8e7e6;
        border-radius: 100px;
        position: absolute;
        top: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
        color: #babab8;
        transform: translateY(-55%);
        cursor: pointer;
        transition: color 0.3s ease;
    }
    .scroll-button:hover {
        color: black;
    }
    .scroll-button-left {
        left: -27.5px;
    }
    .scroll-button-right {
        right: -27.5px;
    }
    .scroll-chevron {
        font-size: 36px;
    }

</style>