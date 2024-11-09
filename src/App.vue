<script setup>
import CardsFile from "./components/Cardsfile.vue";
import { NButton } from "naive-ui";
import { cards } from "../public/card.js";
import { ref, computed, provide } from "vue";
import { NSpace } from "naive-ui";
import WechatIcons from "./components/wechaticons.vue";
import { NButtonGroup } from "naive-ui";
import totop from "./components/totop.vue";
import menulist from "./components/menulist.vue";
import stylebutton from "./components/stylebutton.vue";




// 唯一标签列表
const uniqueTags = Array.from(new Set(cards.flatMap((card) => card.tags)));

const selectedTag = ref(null);

const filteredCards = computed(() => {
  if (!selectedTag.value) return cards;
  return cards.filter((card) => card.tags.includes(selectedTag.value));
});

// 提供filteredCards给下级组件
provide("filteredCards", filteredCards);

function handleSelectTag(tag) {
  selectedTag.value = tag;
}

const navigate = () => {
  window.location.href = "https://wk8686.top";
};
</script>

<template>
  <div >
    <totop />
    <menulist class="mb-4"/>
    <header>
      <WechatIcons />
      <n-space class="mb-12   tagslist">
        <n-button type="info" @click="navigate('https://wk8686.top')"
          >返回主页</n-button
        >
        <n-button type="info" @click="handleSelectTag(null)">显示所有</n-button>
        <n-button
          v-for="tag in uniqueTags"
          :key="tag.id"
          @click="handleSelectTag(tag)"
        >
          {{ tag }}
        </n-button>
      </n-space>
    </header>
    <main>
      <CardsFile :cards="filteredCards" />
      <stylebutton />
    </main>
  </div>
</template>



<style scoped>

</style>
