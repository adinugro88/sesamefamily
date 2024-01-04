<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div>

    <h1 style="font-size: 40px;font-weight: 900;">
      Sesame Street Familiy
    </h1>
    <div  :style="buttonContainerStyle">
      <button class="button1 " @mouseover="showTooltip[1] = true" @mouseleave="showTooltip[1] = false" @click="changeImage">
        <span class="fa fa-star"></span>
       Elmo
        <div v-if="showTooltip[1]" class="tooltip" :style="tooltipPosition" >
          Munculkan Elmo
        </div>
      </button>

      <button class="button2" @mouseover="showTooltip[2] = true" @mouseleave="showTooltip[2] = false" @click="changeImage2">
        <span class="fa fa-heart"></span>
        Cookie Monster
        <div v-if="showTooltip[2]" class="tooltip" :style="tooltipPosition">
          Munculkan Cookie Monster
        </div>
      </button>

      <button class="button3" @mouseover="showTooltip[3] = true" @mouseleave="showTooltip[3] = false" @click="changeImage3">
        <span class="fa fa-check"></span>
       Big Bird
        <div v-if="showTooltip[3]" class="tooltip" :style="tooltipPosition">
          Munculkan Big Bird
        </div>
      </button>
    </div>
    <img :src="gambar" style="width:300px;margin-top: 100px;" alt="" @click="reset">
  </div>
</template>


<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      showTooltip: { 1: false, 2: false, 3: false },
      gambar:'https://m.media-amazon.com/images/M/MV5BODM4NDI3OTcxN15BMl5BanBnXkFtZTgwNjc3MjIwMTI@._V1_FMjpg_UX1000_.jpg'
    };
  },
  computed: {
    tooltipPosition() {
      return { top: '45%', left: '15%' };
    },
    buttonContainerStyle() {
      return {
        display: 'flex',
        gap: '10px',
      };
    },
  },
  methods: {
    buttonClass(size: string) {
      return `button-${size}`;
    },
      changeImage() {
          this.gambar = 'https://2.bp.blogspot.com/-xLKMykb_Y54/Tn9Z6_psnPI/AAAAAAAAAck/8eo_fBbXH6k/s1600/elmo+grande.jpg';
      },
      changeImage2() {
          this.gambar = 'https://pha-cms.s3.amazonaws.com/image/420/medium.jpg?1493411535';
      },
          changeImage3() {
          this.gambar = 'https://www.middlebury.edu/sites/www.middlebury.edu/files/styles/432x576/public/2019-08/big-bird-portrait_0.jpg?fv=TWDxoc-g&itok=FRZ8uIl8';
      },
      reset(){
        this.gambar ='https://m.media-amazon.com/images/M/MV5BODM4NDI3OTcxN15BMl5BanBnXkFtZTgwNjc3MjIwMTI@._V1_FMjpg_UX1000_.jpg'
      }
  },
});
</script>

<style >
.button1 {
  font-size: 12px;
  background-color: red;
  padding: 10px;
  color:white;
  border-radius: 10px;
  font-weight: 900;
  width:100px;
  border: 5px solid black;
}

.button2 {
  font-size: 20px;
  background-color: blue;
  padding: 10px;
  color:white;
  border-radius: 20px;
  font-weight: 900;
  width:200px;
  border: 5px solid black;
}

.button3 {
  font-size: 30px;
  background-color: yellow;
  padding: 10px;
  color:black;
  border-radius: 30px;
  font-weight: 900;
  width:200px;
  border: 5px solid black;
}
.button-small{
  font-size: 16px;
}

.button-medium {
  font-size: 16px;
}

.button-large {
  font-size: 20px;
}

.tooltip {
  position: absolute;
  background-color: #333;
  top:10px;
  color: #fff;
  padding: 5px;
  border-radius: 5px;
  z-index: 1;
}
.full{
  width: 100%;
  height: 100vh;
}
h1{}


body{
  background-image: url('https://img.freepik.com/premium-photo/blurred-colorful-wallpaper-background_976742-179.jpg');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  align-content: center;
  text-align: center;
}
</style>

