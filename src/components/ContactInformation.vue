<template>
  <div class="row my-4">
    <div class="col-md-5 col-12 text-center">
      <img
        class="rounded-circle"
        src="@/assets/Avatar.png"
        style="max-height: 200px"
        alt=""
      />
    </div>
    <div class="col-md-7 col-12">
      <div>
        <span class="fs-1 fw-bolder">李岳峰</span>
        <span class="fs-4 ms-2">(Yueh-Feng, Lee)</span>
      </div>
      <div class="mt-3">
        <span class="badge rounded-pill contact-badge badge-birthday lh-sm fs-5 m-1 text-dark">
          <svg viewBox="0 0 24 24" style="width: 16px; fill: #fc5c65;">
            <path :d="mdiCake" />
          </svg>
          2002-08-24
        </span>

        <a href="mailto:yuehfeng226@gmail.com">
          <span class="badge rounded-pill contact-badge badge-email lh-sm fs-5 m-1">
            <svg viewBox="0 0 24 24" style="width: 16px; fill: #3867d6;">
              <path :d="mdiEmail" />
            </svg>
            yuehfeng226@gmail.com
          </span>
        </a>

        <a href="tel:0905267005">
          <span class="badge rounded-pill contact-badge badge-telphone lh-sm fs-5 m-1">
            <svg viewBox="0 0 24 24" style="width: 16px; fill: #117e47;">
              <path :d="mdiPhone" />
            </svg>
            0905267005
          </span>
        </a>

        <a href="https://github.com/yuehfeng" target="_blank">
          <span class="badge rounded-pill contact-badge badge-github lh-sm fs-5 m-1 text-dark">
            <svg viewBox="0 0 24 24" style="width: 16px; fill: #24292e;">
              <path :d="mdiGithub" />
            </svg>
            https://github.com/yuehfeng
          </span>
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
import { mdiEmail, mdiCake, mdiPhone, mdiGithub } from "@mdi/js";
</script>
