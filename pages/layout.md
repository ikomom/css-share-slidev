---
title: 布局
---

# 布局

#### 如何实现居中效果？

<v-clicks>

margin: auto可以实现**水平居中**

<p>
在 flex 格式化上下文中，设置了 margin: auto 的元素，在通过 justify-content 和 align-self 进行对齐之前

任何正处于**空闲的空间**都会分配到该方向的自动 margin 中去， 实现**垂直居中**效果

</p>
<iframe height="280" style="width: 100%;" scrolling="no" title="最便捷的垂直居中方式 -- flex + margin:auto" src="https://codepen.io/ikomom/embed/PoXQRjg?default-tab=html%2Cresult&editable=true" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/ikomom/pen/PoXQRjg">
  最便捷的垂直居中方式 -- flex + margin:auto</a> by ikomom (<a href="https://codepen.io/ikomom">@ikomom</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

</v-clicks>

---

# 导航栏

<img src="https://chokcoco.github.io/demo/ppt/images/cssmagic/bg-margin.png">

```html
<style>
    .g-nav {
        display: flex;
    }
    .g-login {
        margin-left: auto;
    }
</style>
<body>
    <ul class="g-nav">
        <li>导航A</li>
        <li>导航B</li>
        <li>导航C</li>
        <li>导航D</li>
        <li class="g-login">登陆</li>
        <li>注册</li>
    </ul>
</body>
```

---

# 底栏固定

<iframe height="450" style="width: 100%;" scrolling="no" title="layout-bottom-fixed" src="https://codepen.io/ikomom/embed/gOZveeJ?default-tab=html%2Cresult&editable=true" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/ikomom/pen/gOZveeJ">
  layout-bottom-fixed</a> by ikomom (<a href="https://codepen.io/ikomom">@ikomom</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

---

# 不规则布局

如何实现不规则布局效果? 比如平行四边形、三角形、多边形?

<v-clicks>

 - 使用多个div, 之后用transform拼接 
   - 缺点是图形内部如果还有文字，无法正常排版
 - 使用[clip-path](https://developer.mozilla.org/zh-CN/docs/Web/CSS/clip-path)切割外部形状，结合[shape-outside](https://developer.mozilla.org/zh-CN/docs/Web/CSS/shape-outside)定义了一个**非矩形的形状**，相邻的内联内容围绕该形状进行排版
   - 缺点是[兼容性](https://caniuse.com/?search=clip-path)
</v-clicks>

<div v-click flex gap-2>
   <div flex-1>
```scss
.polygon2 {
   clip-path: polygon(0 0, 400px 0, 500px 300px, 100px 300px);

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
```
   </div>
   <!-- ./components/ShapeOutSideDemo.vue -->
   <ShapeOutSideDemo flex-1/>
</div>

---
layout: full
---

# 图文混排
<iframe src="https://codepen.io/netsi1964/embed/gLvyxj/?height=265&theme-id=1&default-tab=result" width="100%" height="95%"/>
