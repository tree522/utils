<template>
  <div>
    <div>多彩的按钮</div>
    <a href="#" class="color-button">button</a>
  </div>
</template>
<style scoped>
.color-button {
  position: relative;
  display: inline-block;
  width: 200px;
  height: 60px;
  line-height: 60px;
  background-color: skyblue;
  color: #fff;
  text-align: center;
  text-decoration: none;
  background: linear-gradient(90deg, #03a9f4, #f441a5, #ffeb3b, #03a9f4);
  background-size: 400%;
  border-radius: 10px;
}
.color-button:hover {
  animation: animate 8s linear infinite;
}
@keyframes animate {
  0% {
    background-position: 0 0;
  }
  100% {
    background-position: 400% 0;
  }
}
.color-button:before {
  content: "";
  position: absolute;
  left: -5px;
  top: -5px;
  right: -5px;
  bottom: -5px;
  z-index: -1;
  background: linear-gradient(90deg, #03a9f4, #f441a5, #ffeb3b, #03a9f4);
  background-size: 400%;
  border-radius: 10px;
  opacity: 0;
  transition: all 1s;
}
.color-button:hover:before {
  filter: blur(20px);
  opacity: 1;
}
</style>
