<script setup>
import { NButton } from 'naive-ui';
import {cards} from "../../public/card.js";


const uniqueTags = Array.from(new Set(cards.flatMap(card => card.tags)));
const tagCounts = cards.flatMap(card => card.tags).reduce((acc, tag) => {
  acc[tag] = (acc[tag] || 0) + 1;
  return acc;
}, {});


</script>

<template>

<n-space>
    <n-button  v-for="tag in uniqueTags" :key="tag.id">
      {{ tag }}
    </n-button>
  </n-space>
</template>