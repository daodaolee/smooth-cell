<script lang="ts" setup>
const bgArr = ['#818cf8', '#38bdf8', '#34d399', '#facc15']
</script>

<template>
  <div h-screen w-screen class="page">
    <div v-for="(index) in 1000" :key="index" class="grid">
      <div class="cell" index="1" :style="{ '--bg': bgArr[Math.floor(Math.random() * bgArr.length)] }" />
      <div class="cell" index="2" :style="{ '--bg': bgArr[Math.floor(Math.random() * bgArr.length)] }" />
      <div class="cell" index="3" :style="{ '--bg': bgArr[Math.floor(Math.random() * bgArr.length)] }" />
      <div class="cell" index="4" :style="{ '--bg': bgArr[Math.floor(Math.random() * bgArr.length)] }" />
    </div>
  </div>
</template>

<style lang="css">
.page{
  display: grid;
  border-right: 1px;
  border-top: 1px;
  grid-template-columns: repeat(30, 1fr);
  grid-template-rows: repeat(30, 1fr);
  position: fixed;
  top: 5%;
  left: 58%;
  transform: translate(-50%, -50%) skewX(-46deg) skewY(15deg) scaleX(2) scale(0.58) rotate(0) translateZ(0);
}
.grid{
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(2, 1fr);
  width: 80px;
  height: 80px;
  position: relative;
  -webkit-user-select: none;
  user-select: none;
}
.cell{
  transition: opacity 250ms ease-out,  background 2s ease;
  background: transparent;
  border: 1px solid #ededed;
  border-top:0;
  border-right:0;
}
.cell:active{
  transition: background 0s ease;
  background: var(--bg)
}
.cell:hover{
  transition: background 0s ease;
  background: var(--bg)
}
.cell[index="1"]{
  position: relative;
}
.cell[index="1"]:after{
  content:"+";
  display: inline-block;
  position: absolute;
  color:#999;
  top: -30%;
  left: -12%;
  z-index: 2;
}
</style>
