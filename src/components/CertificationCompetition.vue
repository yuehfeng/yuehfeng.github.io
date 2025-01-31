<template>
    <div class="h2 fw-bolder text-secondary d-flex align-items-center my-4">
        <svg viewBox="0 0 24 24" style="width: 32px; fill: #6c757d;">
            <path :d="mdiCertificate" />
        </svg>
        <span class="ms-2">證照與競賽</span>
    </div>
    <div class="row my-2">
        <div class="col-md-3 col-6">
            <div class="card text-bg-dark">
                <img src="@/assets/certs/project.jpg" class="card-img certificate-img" alt="2023年臺中科技大學資訊流通學院專題競賽大學部第二名">
                <div class="card-img-overlay">
                    <h5 class="card-title fw-bolder">2023年臺中科技大學資訊流通學院專題競賽大學部第二名</h5>
                </div>
            </div>
        </div>
        <div class="col-md-3 col-6">
            <div class="card text-bg-dark">
                <img src="@/assets/certs/jlptn2.jpg" class="card-img certificate-img" alt="日本語能力試驗JLPT N2合格">
                <div class="card-img-overlay">
                    <h5 class="card-title fw-bolder">日本語能力試驗JLPT N2合格</h5>
                </div>
            </div>
        </div>
        <div class="col-md-3 col-6">
            <div class="card text-bg-dark">
                <img src="@/assets/certs/erp.jpg" class="card-img certificate-img" alt="鼎新ERP軟體應用師配銷模組">
                <div class="card-img-overlay">
                    <h5 class="card-title fw-bolder">鼎新ERP軟體應用師配銷模組</h5>
                </div>
            </div>
        </div>
        <div class="col-md-3 col-6">
            <div class="card text-bg-dark">
                <img src="@/assets/certs/south1.png" class="card-img certificate-img" alt="第50屆全國技能競賽南區分區賽網頁技術職類第一名">
                <div class="card-img-overlay">
                    <h5 class="card-title fw-bolder">第50屆全國技能競賽南區分區賽網頁技術職類第一名</h5>
                </div>
            </div>
        </div>
    </div>
    <div class="row my-2">
        <div class="col-md-6 col-6 text-center">
            <div class="card text-bg-dark col-md-8 mx-auto">
                <img src="@/assets/certs/webdesignB.jpg" class="card-img certificate-img" alt="勞動部網頁設計乙級(編號:173-000065)">
                <div class="card-img-overlay">
                    <h5 class="card-title fw-bolder">勞動部網頁設計乙級(編號:173-000065)</h5>
                </div>
            </div>
        </div>
        <div class="col-md-6 col-6 text-center">
            <div class="card text-bg-dark col-md-8 mx-auto">
                <img src="@/assets/certs/softwareB.jpg" class="card-img certificate-img" alt="勞動部電腦軟體應用乙級(編號:118-161999)">
                <div class="card-img-overlay">
                    <h5 class="card-title fw-bolder">勞動部電腦軟體應用乙級(編號:118-161999)</h5>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { mdiCertificate } from "@mdi/js";
</script>