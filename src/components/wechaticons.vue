<template>
  <div class="absolute right-0 w-1/3 iconall top-2">
  
    <span>
    <a href="https://github.com/KangWang42/01-zotplug" target="_blank">
      <img
        src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png"
        alt="GitHub"
        width="40"
        height="40"
         class="absolute top-3 right-72 transition ease-in-out delay-150 hover:scale-125 duration-300"
      />
    </a>
  </span>
  <div class="absolute cursor-pointer right-52 top-4 inline-block group">
    <!-- 小尺寸的 SVG 微信图标 -->
    <svg
      t="1730884416770"
      class="hover:scale-125 w-10 h-10 text-green-500 transition ease-in-out duration-300"
      viewBox="0 0 1024 1024"
      xmlns="http://www.w3.org/2000/svg"
      fill="#00C800"
    >
      <path
        d="M1010.8 628c0-141.2-141.3-256.2-299.9-256.2-168 0-300.3 115.1-300.3 256.2 0 141.4 132.3 256.2 300.3 256.2 35.2 0 70.7-8.9 106-17.7l96.8 53-26.6-88.2c70.9-53.2 123.7-123.7 123.7-203.3zM618 588.8c-22.1 0-40-17.9-40-40s17.9-40 40-40 40 17.9 40 40c0 22-17.9 40-40 40z m194.3-0.3c-22.1 0-40-17.9-40-40s17.9-40 40-40 40 17.9 40 40-17.9 40-40 40z"
      />
      <path
        d="M366.3 106.9c-194.1 0-353.1 132.3-353.1 300.3 0 97 52.9 176.6 141.3 238.4l-35.3 106.2 123.4-61.9c44.2 8.7 79.6 17.7 123.7 17.7 11.1 0 22.1-0.5 33-1.4-6.9-23.6-10.9-48.3-10.9-74 0-154.3 132.5-279.5 300.2-279.5 11.5 0 22.8 0.8 34 2.1C692 212.6 539.9 106.9 366.3 106.9zM247.7 349.2c-26.5 0-48-21.5-48-48s21.5-48 48-48 48 21.5 48 48-21.5 48-48 48z m246.6 0c-26.5 0-48-21.5-48-48s21.5-48 48-48 48 21.5 48 48-21.5 48-48 48z"
      />
    </svg>

    <!-- 悬浮显示的较大二维码图片 -->
    <img
      src="https://pic-go-42.oss-cn-guangzhou.aliyuncs.com/img/202411061710319.webp"
      alt="WeChat QR Code"
      class="hidden group-hover:block fixed top-20 right-2 transform -translate-x-1/2 w-60 border border-gray-300 rounded-lg shadow-lg z-10"
    />
  </div>
  
  </div>
</template>

<style scoped>
@media (max-width: 850px) {
  .iconall{
 display: none;
}
  
}


</style>
