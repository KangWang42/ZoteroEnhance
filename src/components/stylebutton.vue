<template>
  <n-config-provider :theme="theme">
    <n-card>
      <n-space>
        <n-button @click="theme = darkTheme"> 深色 </n-button>
        <n-button @click="theme = null"> 浅色 </n-button>
      </n-space>
    </n-card>
  </n-config-provider>
</template>
  
  <script setup>
import { defineComponent, ref } from "vue";
import { darkTheme } from "naive-ui";

import { NButton } from "naive-ui";
import { NSpace, NConfigProvider, NCard } from "naive-ui";
</script>