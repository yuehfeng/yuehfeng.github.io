<template>
  <div>
    <div class="timeline">
      <div
        class="timeline__event animated fadeInUp delay-1s timeline__event--type2"
      >
        <div class="timeline__event__icon">
        </div>
        <div class="timeline__event__content">
          <div class="timeline__event__title">
            <svg viewBox="0 0 24 24" style="width: 20px; fill: #555ac0;">
              <path :d="mdiSchool" />
            </svg>
            大學
          </div>
          <div class="timeline__event__description">
            <span class="fs-5 fw-bold">國立臺中科技大學</span>
            <span class="fs-5 mx-1">資訊管理系</span>
            <span class="fs-5">學士</span>
          </div>
        </div>
      </div>
      <div
        class="timeline__event animated fadeInUp timeline__event--type3"
      >
        <div class="timeline__event__icon">
        </div>
        <div class="timeline__event__content">
          <div class="timeline__event__title">
            <svg viewBox="0 0 24 24" style="width: 20px; fill: #24292e;">
              <path :d="mdiSchoolOutline" />
            </svg>
            高職
          </div>
          <div class="timeline__event__description">
            <span class="fs-5 fw-bold">高雄市立海青高級工商職業學校</span>
            <span class="fs-5 mx-1">資料處理科</span>
            <span class="fs-5">畢業</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import "@/assets/education_style.scss";
import { mdiSchool, mdiSchoolOutline } from "@mdi/js";
</script>