<style scoped>
  .tabs {
    display: flex;
    flex-wrap: wrap;
    position: relative;
    background-color: #fff;
    box-shadow: 0 0 1px 0 rgba(24, 94, 224, 0.15), 0 6px 12px 0 rgba(24, 94, 224, 0.15);
    padding: 0.75rem;
    border-radius: 99px;
  }

  .tabs * {
    z-index: 2;
  }
  .container {
   margin-left: 20px;
  }
  


  .container input[type="radio"] {
    display: none;
  }

  .tab {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 30px;
    width: 100px;
    font-size: 1.1rem;
    color: rgb(75, 36, 36);
    font-weight: 700;
    border-radius: 99px;
    cursor: pointer;
    transition: color 0.15s ease-in;
  }

  .notification {
    display: flex;
    align-items: center;
    justify-content: center;
    width: .8rem;
    height: .8rem;
    position: absolute;
    top: 10px;
    left: 30%;
    font-size: 10px;
    margin-left: 0.75rem;
    border-radius: 50%;
    margin: 0px;
    background-color: #e6eef9;
    transition: 0.15s ease-in;
  }

  .container input[type="radio"]:checked + label {
    color: #185ee0;
  }

  .container input[type="radio"]:checked + label > .notification {
    background-color: #185ee0;
    color: #fff;
    margin: 0px;
  }

  .container input[id="radio-1"]:checked ~ .glider {
    transform: translateX(0);
  }

  .container input[id="radio-2"]:checked ~ .glider {
    transform: translateX(100%);
  }

  .container input[id="radio-3"]:checked ~ .glider {
    transform: translateX(200%);
  }

  .glider {
    position: absolute;
    display: flex;
    height: 30px;
    width: 95%;
    background-color: #fbfbfb;
    z-index: 1;
    border-radius: 99px;
    transition: 0.25s ease-out;
  }

  @media (max-width: 700px) {
   .container{
    margin-left: 0px;

   }

    .tabs{
        margin-left: 0px;
        display: flex;
        row-gap: 30px;
        column-gap: 10px;
        justify-content:space-around;
       padding-left: 20px;
       padding-right: 20px;
       border-radius: 10px;
       margin-top: 20px;

    }

    .tab{
       font-size: 1.3em;
    }
    span.glider{
        display: none;

    }

  }
</style>

<template>
<div class="container">
    <div class="tabs ">
      <div v-for="(item, index) in items" :key="item.id">
        <input 
          type="radio" 
          :id="`radio-${index + 1}`" 
          name="tabs" 
          :checked="index === 0"
          @click="handleClick(item)"
        />
        <label class="tab" :for="`radio-${index + 1}`">
          {{ item}}
          <span v-if="item.notification" class="notification">"xxx"</span>
        </label>
      </div>
      <span class="glider"></span>
    </div>
  </div>
</template>


<script setup>
defineProps({
  items: {
    type: Array,
    required: true
  }
});

const emit = defineEmits(['click']);

const handleClick = (item) => {
  emit('click', item); // 发射事件并传递数据
};
</script>