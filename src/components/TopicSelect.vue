<template>
  <div class="flex m-2 justify-center flex-wrap">
    <button 
      class="text-base rounded-r-none 
      hover:scale-110 focus:outline-none 
      flex justify-center px-4 py-2 
      rounded font-bold cursor-pointer 
      hover:bg-yellow-400 hover:text-slate-800 
      active:bg-yellow-400 bg-gray-200 
      text-slate-800
      border duration-200 ease-in-out 
      border-slate-800 transition"
      :style="{'background-color': currentTopic === 'general' ? color : ''}"
      v-on:click="selected('general')"
    >
      <div class="flex leading-5">
        General
      </div>
    </button>
    <button class="text-base rounded-l-none rounded-r-none border-l-0
      hover:scale-110 focus:outline-none flex justify-center px-4 py-2 
      rounded font-bold cursor-pointer 
      hover:bg-yellow-400 hover:text-slate-800 
      bg-gray-200 
      text-slate-800
      border duration-200 ease-in-out 
      border-slate-800 transition"
      :style="{'background-color': currentTopic === 'entertainment' ? color : ''}"
      v-on:click="selected('entertainment')"
    >
      <div class="flex leading-5">
        Entertainment
      </div>
    </button>
    <button class="text-base rounded-l-none rounded-r-none border-l-0
      hover:scale-110 focus:outline-none flex justify-center px-4 py-2 
      rounded font-bold cursor-pointer 
      hover:bg-yellow-400 hover:text-slate-800 
      bg-gray-200 
      text-slate-800
      border duration-200 ease-in-out 
      border-slate-800 transition"
      :style="{'background-color': currentTopic === 'business' ? color : ''}"
      v-on:click="selected('business')"
    >
      <div class="flex leading-5">
        Business
      </div>
    </button>
    <button class="text-base rounded-l-none rounded-r-none border-l-0
      hover:scale-110 focus:outline-none flex justify-center px-4 py-2 
      rounded font-bold cursor-pointer 
      hover:bg-yellow-400 hover:text-slate-800 
      bg-gray-200 
      text-slate-800
      border duration-200 ease-in-out 
      border-slate-800 transition"
      :style="{'background-color': currentTopic === 'health' ? color : ''}"
      v-on:click="selected('health')"
    >
      <div class="flex leading-5">
        Health
      </div>
    </button>
    <button class="text-base rounded-l-none rounded-r-none border-l-0
      hover:scale-110 focus:outline-none flex justify-center px-4 py-2 
      rounded font-bold cursor-pointer 
      hover:bg-yellow-400 hover:text-slate-800 
      bg-gray-200 
      text-slate-800
      border duration-200 ease-in-out 
      border-slate-800 transition"
      :style="{'background-color': currentTopic === 'science' ? color : ''}"
      v-on:click="selected('science')"
    >
      <div class="flex leading-5">
        Science
      </div>
    </button>
    <button class="text-base rounded-l-none rounded-r-none border-l-0 border-r-0 
      hover:scale-110 focus:outline-none flex justify-center px-4 py-2 
      rounded font-bold cursor-pointer 
      hover:bg-yellow-400 hover:text-slate-800 
      bg-gray-200 
      text-slate-800
      border duration-200 ease-in-out 
      border-slate-800 transition"
      :style="{'background-color': currentTopic === 'sports' ? color : ''}"
      v-on:click="selected('sports')"
    >
      <div class="flex leading-5">
        Sports
      </div>
    </button>
    <button class="text-base rounded-l-none hover:scale-110 focus:outline-none 
      flex justify-center px-4 py-2 rounded font-bold cursor-pointer 
      hover:bg-yellow-400 hover:text-slate-800 
      bg-gray-200 
      text-slate-800
      border duration-200 ease-in-out 
      border-slate-800 transition"
      :style="{'background-color': currentTopic === 'technology' ? color : ''}"
      v-on:click="selected('technology')"
    >
      <div class="flex leading-5">
        Technology
      </div>
    </button>
  </div>
</template>

<script>
export default {
  name: 'TopicSelect',
  data() {
    return {
      currentTopic: '',
      color: '#ca8a04'
    }
  },
  methods: {
    selected(value) {
      this.currentTopic = value;
      console.log("Selected topic: ", value);
      this.$emit('get-topic', value);
    }
  }
}
</script>