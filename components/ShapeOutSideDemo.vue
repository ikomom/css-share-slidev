<script setup>

</script>

<template>
  <div  class="polygon2">
    <span class="left"></span>
    <span class="right"></span>
    <p>
      1. shape-outside 定义了一个可以是非矩形的形状，相邻的内联内容应围绕该形状进行排版。<br>
      2. shape-outside 属性指定使用下面列表的值来定义浮动元素的浮动区域。这个浮动区域决定了行内内容（浮动元素）所包裹的形状。<br>
      3. clip-path CSS 属性可以创建一个只有元素的部分区域可以显示的剪切区域。<br>
    </p>
  </div>

</template>

<style scoped>
.polygon2 {
  margin-top: 50px;
  width: 400px;
  height: 200px;
  overflow: hidden;
  background: #ffcc00;
  line-height: 42px;
  clip-path: polygon(0 0, 300px 0, 400px 300px, 100px 300px);
  text-align: left;

  span {
    width: 100px;
    height: 300px;
  }
  .right {
    float: right;
    shape-outside: polygon(0px 0px, 100px 0px, 100px 300px);
    clip-path: polygon(0px 0px, 100px 0px, 100px 300px);
  }

  .left {
    float: left;
    shape-outside: polygon(0px 0px, 0px 300px, 100px 300px);
    clip-path: polygon(0px 0px, 0px 300px, 100px 300px);
  }

}
</style>
