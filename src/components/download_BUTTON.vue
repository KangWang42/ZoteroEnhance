<style scoped>
  .Btn {
    width: 35px;
    height: 35px;
    border: none;
    border-radius: 50%;
    margin-left: 5px;
    background-color: rgb(189, 219, 245);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    position: relative;
    transition-duration: .3s;
    box-shadow: 2px 2px 10px rgba(104, 133, 214, 0.11);
  }

  .svgIcon {
    fill: rgb(56, 58, 41);
  }

  .icon2 {
    width: 18px;
    height: 5px;
    border-bottom: 2px solid rgb(90, 102, 180);
    border-left: 2px solid rgb(90, 102, 180);
    border-right: 2px solid rgb(90, 102, 180);
  }

  .tooltip {
    position: absolute;
    right: -105px;
    opacity: 0;
    background-color: rgb(12, 12, 12);
    color: white;
    padding: 5px 10px;
    border-radius: 5px;
    display: flex;
    align-items: center;
    justify-content: center;
    transition-duration: .2s;
    pointer-events: none;
    letter-spacing: 0.5px;
  }

  .tooltip::before {
    position: absolute;
    content: "";
    width: 10px;
    height: 10px;
    background-color: rgb(12, 12, 12);
    background-size: 1000%;
    background-position: center;
    transform: rotate(45deg);
    left: -5%;
    transition-duration: .3s;
  }

  .Btn:hover .tooltip {
    opacity: 1;
    transition-duration: .3s;
  }

  .Btn:hover {
    background-color: rgb(61, 116, 234);
    transition-duration: .3s;
  }

  .Btn:hover .icon2 {
    border-bottom: 2px solid rgb(235, 235, 235);
    border-left: 2px solid rgb(235, 235, 235);
    border-right: 2px solid rgb(235, 235, 235);
  }

  .Btn:hover .svgIcon {
    fill: rgb(255, 255, 255);
    animation: slide-in-top 0.6s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
  }

  @keyframes slide-in-top {
    0% {
      transform: translateY(-10px);
      opacity: 0;
    }

    100% {
      transform: translateY(0px);
      opacity: 1;
    }
  }
</style>

<template>
  <button class="Btn">
     <svg class="svgIcon" viewBox="0 0 384 512" height="1em" xmlns="http://www.w3.org/2000/svg"><path d="M169.4 470.6c12.5 12.5 32.8 12.5 45.3 0l160-160c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L224 370.8 224 64c0-17.7-14.3-32-32-32s-32 14.3-32 32l0 306.7L54.6 265.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3l160 160z"></path></svg>
     <span class="icon2"></span>
     <span class="tooltip">点击下载</span>
  </button>
</template>
