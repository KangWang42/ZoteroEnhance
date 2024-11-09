<template>
  <n-button @click="handleClick">
    点它
  </n-button>
</template>

<script>
import { defineComponent } from "vue";
import { useMessage } from "naive-ui";

export default defineComponent({
  setup() {
    const message = useMessage();
    return {
      handleClick() {
        message.info("Button Clicked");
      }
    };
  }
});
</script>