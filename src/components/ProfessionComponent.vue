<template>
    <div class="h2 fw-bolder text-secondary d-flex align-items-center my-4">
        <svg viewBox="0 0 24 24" style="width: 32px; fill: #6c757d;">
            <path :d="mdiBriefcase" />
        </svg>
        <span class="ms-2">專業技能</span>
    </div>
    <transition name="fade">
        <div ref="animatedProfessionSkill" :class="{ animate__animated: skillIsVisible, 'animate__fadeInUp': skillIsVisible }">
            <div class="row my-4">
                <div class="col-auto d-flex align-items-center">
                    <span class="border-4 border-start border-primary ps-2 fs-4 fw-bolder">前端</span>
                </div>
                <div class="col d-flex align-items-center flex-wrap">
                    <span v-for="(frontend, index) in frontends" :key="frontend + index" class="badge text-bg-light fs-6 m-1">
                        {{ frontend }}
                    </span>
                </div>
            </div>
            <div class="row my-4">
                <div class="col-auto d-flex align-items-center">
                    <span class="border-4 border-start border-success ps-2 fs-4 fw-bolder">後端</span>
                </div>
                <div class="col d-flex align-items-center flex-wrap">
                    <span v-for="(backend, index) in backends" :key="backend + index" class="badge text-bg-light fs-6 mx-1">
                        {{ backend }}
                    </span>
                </div>
            </div>
            <div class="row my-4">
                <div class="col-auto d-flex align-items-center">
                    <span class="border-4 border-start border-danger ps-2 fs-4 fw-bolder">資料庫</span>
                </div>
                <div class="col d-flex align-items-center flex-wrap">
                    <span v-for="(database, index) in databases" :key="database + index" class="badge text-bg-light fs-6 mx-1">
                        {{ database }}
                    </span>
                </div>
            </div>
            <div class="row my-4">
                <div class="col-auto d-flex align-items-center">
                    <span class="border-4 border-start border-warning ps-2 fs-4 fw-bolder">開發工具</span>
                </div>
                <div class="col d-flex align-items-center flex-wrap">
                    <span v-for="(devtool, index) in devtools" :key="devtool + index" class="badge text-bg-light fs-6 mx-1">
                        {{ devtool }}
                    </span>
                </div>
            </div>
        </div>
    </transition>
    <div class="h2 fw-bolder text-secondary d-flex align-items-center my-4">
        <svg viewBox="0 0 24 24" style="width: 32px; fill: #6c757d;">
            <path :d="mdiTranslate" />
        </svg>
        <span class="ms-2">語言能力</span>
    </div>
    <transition name="fade">
        <div class="row d-flex" ref="animatedLanguage" :class="{ animate__animated: langIsVisible, 'animate__fadeInUp': langIsVisible }">
            <div class="col-sm-4">
                <div class="card h-100">
                <div class="card-body">
                    <h5 class="card-title fw-bolder">中文</h5>
                    <p class="card-text">母語</p>
                </div>
                </div>
            </div>
            <div class="col-sm-4">
                <div class="card h-100">
                    <div class="card-body">
                        <h5 class="card-title fw-bolder">日文</h5>
                        <div class="card-text">
                            <ul class="list-group list-group-flush">
                                <li class="list-group-item">日本語能力試驗 JLPT N2合格</li>
                                <li class="list-group-item">J.TEST實用日本語檢定 N2同等學力</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-sm-4">
                <div class="card h-100">
                    <div class="card-body">
                        <h5 class="card-title fw-bolder">英文</h5>
                        <p class="card-text">基礎</p>
                    </div>
                </div>
            </div>
        </div>
    </transition>
</template>

<script setup>
import { mdiBriefcase, mdiTranslate } from "@mdi/js";
import { ref } from "vue";

const frontends = ref(["HTML", "CSS", "JavaScript", "Vue", "Angular", "Bootstrap", "Taliwind CSS", "Figma"]);
const backends = ref(["Python", "Golang", "PHP", "Laravel", "Java"]);
const databases = ref(["PostgreSQL", "MySQL"]);
const devtools = ref(["Git", "GitHub", "VS Code", "AWS", "nginx"]);
</script>

<script>
export default {
    data() {
        return {
            skillIsVisible: false,
            langIsVisible: false,
        };
    },
    mounted() {
        const skillObserver = new IntersectionObserver(
            ([entry]) => {
                if (entry.isIntersecting) {
                    this.skillObserver = true; // 當元素進入可視範圍，啟用動畫
                    skillObserver.disconnect(); // 停止觀察
                }
            },
            {
                threshold: 0.1, // 元素可見 10% 時觸發
            }
        );

        skillObserver.observe(this.$refs.animatedProfessionSkill);

        
        const langObserver = new IntersectionObserver(
            ([entry]) => {
                if (entry.isIntersecting) {
                    this.langIsVisible = true; // 當元素進入可視範圍，啟用動畫
                    langObserver.disconnect(); // 停止觀察
                }
            },
            {
                threshold: 0.1, // 元素可見 10% 時觸發
            }
        );

        langObserver.observe(this.$refs.animatedLanguage);
    },
};
</script>

<style scoped>
.fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
}
.fade-enter, .fade-leave-to {
    opacity: 0;
}
</style>