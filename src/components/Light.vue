
<script setup>

import {ref,reactive} from "vue";

const onIcon="//img.icons8.com/?size=512&id=12244&format=png";
const offIcon="//img.icons8.com/?size=512&id=75&format=png";

const lights=reactive(
    [
      {
        light1:'light1',
        offIcon:offIcon,
        onIcon:onIcon,
        lightOn:1,
      },
      {
        light2:'light2',
        offIcon:offIcon,
        onIcon:onIcon,
        lightOn:0,
      },
      {
        light3:'light3',
        offIcon:offIcon,
        onIcon:onIcon,
        lightOn:0,
      },
    ]
);

</script>



<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Assignment</h1>
    <p class="p-5">Make These Buttons Work</p>
    <div class="flex justify-between space-x-6">
      <div class="p-10 border w-96 flex flex-col space-y-5">

        <button @click="light.lightOn=!light.lightOn" :class="light.lightOn?'bg-blue-700':'bg-gray-700'"  class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
                v-for="(light,index) in lights" :key="index">
          Light {{index+1}} {{light.lightOn?'On':'Off'}}
        </button>

      </div>
      <div class="p-10 border w-96 flex flex-col space-y-5">
        <img class="w-20" :src="light.lightOn?light.onIcon:light.offIcon"
             alt="" v-for="(light,index) in lights" :key="index">
      </div>
    </div>
  </section>
</template>



<style scoped>

</style>