<template>
    <div class="h2 fw-bolder text-secondary d-flex align-items-center my-4">
        <svg viewBox="0 0 24 24" style="width: 32px; fill: #6c757d;">
            <path :d="mdiChartTimelineVariant" />
        </svg>
        <span class="ms-2">工作與專案經驗</span>
    </div>
    <ul class="experience" ref="animatedWorkExperience" :class="{ animate__animated: isVisible, 'animate__fadeInUp': isVisible }">
        <li v-for="(exp, index) in experiences" :key="index+exp" :style="'--accent-color:' + exp.theme.bgcolor">
            <div class="date opacity-100 text-dark">{{ exp.title }}</div>
            <div v-if="exp.subtitle != ''" class="title">{{ exp.subtitle }}</div>
            <div class="descr">
                <div class="border-4 border-start border-secondary bg-light ps-3 py-2 fw-bolder mb-2">{{ exp.description }}</div>
                <div><SkillPointer v-for="tag in exp.tags" :key="tag" :name="tag" /></div>
                <div v-if="exp.sources.length > 0">
                    <hr>
                    <span class="fs-6 fw-bold my-2">原始碼</span>
                    <div v-for="source in exp.sources" :key="source">
                        <svg viewBox="0 0 24 24" style="width: 16px; fill: rgba(47, 53, 66, 1.0)">
                            <path :d="mdiCodeTags" />
                        </svg>
                        <a target="_blank" class="ms-2 effect-link" :href="source.link">{{ source.name }}({{ source.link }})</a>
                    </div>
                </div>
                <div class="text-end" v-if="exp.view != ''">
                    <a target="_blank" class="effect-link" :href="exp.view">成果預覽 ></a>
                </div>
            </div>
        </li>
    </ul>
</template> 

<script setup>
import { mdiChartTimelineVariant, mdiCodeTags } from "@mdi/js";
import SkillPointer from "@/components/modules/SkillPointer.vue";
import { ref } from "vue";

const experiences = ref([
    {
        "title": "國立臺中科技大學專任助理暨博士後研究",
        "subtitle": "國科會計畫-產業導向職能視覺化系統",
        "date": "Sep.–Dec. 2024",
        "description": "定期爬蟲人力資源網站，撈取相關產業檢視最新職缺技能，透過批次處理與ChatGPT API的方式產生技能樹；教授身分則由後臺登入，輸入課程使用到的技能並使用公式計算瞭解該課程是否與現行產業接軌，搭配Holland解析亦能讓相關產業之學生瞭解未來就職的roadmap與相性測試。",
        "tags": ["Selenium", "Python", "Vue3", "postgreSQL", "nginx", "Let's Encrypt", "Jira", "Github"],
        "sources": [],
        "theme": {
            "bgcolor": "rgba(252, 92, 101, .1)"
        },
        "view": ""
    },
    {
        "title": "國泰人壽行銷資訊部 後端工程師實習生",
        "date": "Feb.-Jun. 2024",
        "description": "實習期間使用Java Spring Boot進行後端開發，搭配前端Vue框架，分別共同開發兩個子專案、偵錯專案issue以及撰寫底層元件庫。",
        "tags": ["spring boot", "vue2", "vue3", "Jira", "sourcetree"],
        "sources": [],
        "theme": {
            "bgcolor": "rgba(2, 102, 90, .1)"
        },
        "view": "https://patronc.cathaylife.com.tw/ODBF/season_activity?activity_ser_no=3"
    },
    {
        "title": "國科會計畫-計畫資源論文暨資訊推薦平台",
        "date": "Jan. 2024 – May. 2024",
        "description": "定期爬蟲學術論文網站撈取相關產業資料，並透過Bert解析文字表徵與歐式距離，分類資料至對應產業供相關科系教授與學生參考使用。",
        "tags": ["Selenium", "Bert", "Python", "Vue3", "postgreSQL", "nginx", "Let's Encrypt", "Jira", "github"],
        "sources": [],
        "theme": {
            "bgcolor": "rgba(184, 233, 148, .1)"
        },
        "view": ""
    },
    {
        "title": "大學畢業專題",
        "subtitle": "詐騙護手",
        "date": "Oct. 2023 – Jun. 2024",
        "description": "由於詐騙頻傳以及人工智慧應用的流行，對此開發瀏覽器插件以及LINE機器人辨別詐騙可能性的雙重防線。瀏覽器插件，使用者在點擊網站前進行前置檢查網址是否在已知的阻擋清單以及Google安全性檢測，並分析文本可疑性。LINE機器人，可轉傳多則訊息、圖片、聲音等資訊，檢測可疑性。",
        "tags": ["python", "bs4", "Firebase", "Chrome Extensions", "linebot", "vue3", "ChatGPT API", "Google Vision AI", "Blocklist API", "Opendata", "Google Safe Browsing"],
        "sources": [
            {
                "name": "主程式",
                "link": "https://github.com/yuehfeng/ScamProtector"
            },
            {
                "name": "瀏覽器插件",
                "link": "https://github.com/yuehfeng/ScamProtectorExtension"
            },
            {
                "name": "LINE機器人",
                "link": "https://github.com/yuehfeng/ScamProtectorLiff"
            }
        ],
        "theme": {
            "bgcolor": "rgba(10, 61, 98, .1)"
        },
        "view": "https://yuehfeng.github.io/ScamProtectorSite"
    },
    {
        "title": "LINE購物車服務",
        "date": "Dec. 2022 – Apr. 2023",
        "description": "接案網站，以LINE的LIFF購物車服務為主，後端使用Golang，和前端Vue網頁框架進行前後端分離，並透過LINE機器人請求追蹤訂單等。",
        "tags": ["liff", "vue3", "github", "aws"],
        "sources": [],
        "theme": {
            "bgcolor": "rgba(229, 80, 57, .1)"
        },
        "view": "https://shared888.com/1"
    },
    {
        "title": "曼尼購物車網站",
        "date": "Oct. 2022 – Dec. 2022",
        "description": "接案網站，使用Laravel網頁框架並串接藍新金流之購物車網站",
        "tags": ["PHP", "Laravel", "HTML", "CSS", "Javascript"],
        "sources": [],
        "theme": {
            "bgcolor": "rgba(246, 185, 59, .1)"
        },
        "view": "https://mannersandshoes.com.tw/"
    },
    {
        "title": "臺中科技大學語文學院",
        "date": "Oct. 2022 – Dec. 2022",
        "description": "接案網站，使用Laravel網頁框架並串接藍新金流之購物車網站",
        "tags": ["PHP", "Laravel", "Asp.net", "Vue", "HTML", "CSS", "Javascript"],
        "sources": [
            {
                "name": "前端程式",
                "link": "https://github.com/yuehfeng/ntcust_lang_frontend",
            },
            {
                "name": "後端程式",
                "link": "https://github.com/yuehfeng/ntcust_lang_backend",
            },
        ],
        "theme": {
            "bgcolor": "rgba(74, 105, 189, .1)"
        },
        "view": "https://colanguage.nutc.edu.tw/"
    },
    {
        "title": "sugoeat官方網站",
        "date": "Oct. 2020",
        "description": "由起初前端網頁改革至APP版，並將原有的網頁接上Strikingly串上金流並套用LINE@預定功能。",
        "tags": [],
        "sources": [],
        "theme": {
            "bgcolor": "rgba(96, 163, 188, .1)"
        },
        "view": "https://sugoeat.mystrikingly.com/"
    },
    {
        "title": "全國技能競賽網頁技術選手",
        "date": "Jan. 2019 - Oct. 2020",
        "description": "高職階段擔任網頁設計選手，針對分區賽、全國賽題目全方面訓練。",
        "tags": ["HTML", "CSS", "Javascript", "XAMPP", "PHP", "MariaDB", "Laravel", "Vue2", "SPA pages"],
        "sources": [],
        "theme": {
            "bgcolor": "rgba(235, 47, 6, .1)"
        },
        "view": ""
    }
]);
</script>

<script>
export default {
    data() {
        return {
            isVisible: false, // 控制是否啟用動畫
        };
    },
    mounted() {
        const observer = new IntersectionObserver(
            ([entry]) => {
                if (entry.isIntersecting) {
                    this.isVisible = true; // 當元素進入可視範圍，啟用動畫
                    observer.disconnect(); // 停止觀察
                }
            },
            {
                threshold: 0.1, // 元素可見 10% 時觸發
            }
        );

        observer.observe(this.$refs.animatedWorkExperience);
    },
};
</script>

<style scoped>
@import "@/assets/experience_style.css";
.fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
}
.fade-enter, .fade-leave-to {
    opacity: 0;
}
</style>