<style scoped>
  .n-menu {
    height: 100%;
  }

  /*设置menu的背景颜色和样式优雅*/
  .n-menu{
    background-color:antiquewhite;
  }


</style>

<template>
    <n-split :default-size="0.8">
      <template #1>
        <n-menu
          v-model:value="activeKey"
          mode="horizontal"
          :options="menuOptions"
          responsive
        />
      </template>
    </n-split>
  </template>

  <script setup>
    import { NMenu,NSplit } from "naive-ui";
  import { defineComponent, h, ref } from "vue";
  import { NIcon } from "naive-ui";
  import {
    BookOutline as BookIcon,
    PersonOutline as PersonIcon,
    WineOutline as WineIcon,
    Bookmark
  } from "@vicons/ionicons5";
  
  function renderIcon(icon) {
    return () => h(NIcon, null, { default: () => h(icon) });
  }
  
  const menuOptions = [
    { label: () => h(
        "a",
        {
          href: "https://wk8686.top",
          target: "_blank",
          rel: "noopenner noreferrer"
        },
        "返回博客"
      ),
      key: "hear-the-wind-sing",
      icon: renderIcon(BookIcon)
    },
    {
        label: () => h(
        "a",
        {
          href: "https://intro.wk8686.top",
          target: "_blank",
          rel: "noopenner noreferrer"
        },
        "查看我的主页"
      ),
      key: "pinball-1973",
      icon: renderIcon(PersonIcon)
    },
    {
      label:  () => h(
        "a",
        {
          href: "https://zottheme.wk8686.top",
          target: "_blank",
          rel: "noopenner noreferrer"
        },
        "查看zotero笔记主题"
      ),
      key: "dance-dance-dance",
      icon: renderIcon(Bookmark)
    }
  ];
  


  </script>