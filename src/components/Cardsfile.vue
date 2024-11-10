<script setup>
import { inject } from "vue";
import { NCard, NTag, NSpace, NButton, NIcon } from "naive-ui";
import { LogInOutline as LogInIcon } from "@vicons/ionicons5";
import { NButtonGroup } from "naive-ui";

const filteredCards = inject("filteredCards"); // 确保注入正确

function handleClick(link) {
  window.location.href = link; // 操作链接的函数
}

</script>

<template>
  <div class="flex flex-wrap  gap-y-20 gap-x-1 justify-around cardwrap  ">
    <div
      v-for="card in filteredCards"
      :key="card.id"
      class="rounded-2xl card-list w-1/4 min-w-80 "
    >
      <n-card :title="card.title" class="hover:shadow-2xl">
        <template #default>
          <img
            :src="card.image"
            alt="Card Image"
            class="card-image mb-4 absolute right-0 top-2 w-12 h-12"
          />

          {{ card.details }}
        </template>
        <template #footer>
          <n-space>
            <n-tag v-for="tag in card.tags" :key="tag" type="info">{{
              tag
            }}</n-tag>
          </n-space>
        </template>
        <template #action>
          <n-button-group class="flex justify-around pt-5 border-t-4 w-full">
            <n-button ghost @click="handleClick(card.link)">
              <template #icon>
                <n-icon><LogInIcon /></n-icon>
              </template>
              查看教程
            </n-button>
            <n-button ghost @click="handleClick(card.title_link)">
              <template #icon>
                <n-icon><LogInIcon /></n-icon>
              </template>
              官方仓库
            </n-button>
          </n-button-group>
        </template>
      </n-card>
    </div>
  </div>
</template>

<style scoped>
/* 如果你需要额外的样式调整 */
.px-2 {
  padding-left: 0.5rem;
  padding-right: 0.5rem;
}

.card-list:hover {
  scale: 1.1;
  animation-duration: 800ms;
}

@media (max-width: 768px) {
  .cardwrap.card-list {
    padding: 0;
  }
}
</style>
