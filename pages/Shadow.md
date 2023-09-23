---
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# 阴影

box-shadow

<v-clicks>

<div>
1. 阴影

<p shadow-xl w-50 h-10 bg-red shadow-red>
</p>
</div>

<div>
    2. 内阴影(inset)
<p shadow-xl w-50 h-10 shadow-inset shadow-red>
</p>
</div>

<div>
3. 多重阴影

<p text="3">可以轻松复制对象本身，并且任意改变颜色及大小</p>

<p class="mul"></p>
</div>

</v-clicks>

<style>
    .mul {
    width: 80px;
    height: 80px;
    background: #F87171;
    box-shadow: 
        80px 80px 0 0 yellow, 
        -20px 80px 0 10px green;
}
</style>

---

#### 阴影多重边框

模拟出的边框不占宽度

```css
{
  background: #F8F8F8;
  box-shadow:  
    0 0 0 2px orange,
    0 0 0 4px red,
    0 0 0 6px yellow,
    0 0 0 8px green,
    0 0 0 10px cyan;
}
```
<div class="bgShadow9"></div>

<style>

div.bgShadow9 {
    margin: 50px auto!important;
    width: 120px;
    height: 80px;
    background: #F8F8F8;
  box-shadow:  
    0 0 0 2px orange,
    0 0 0 4px red,
    0 0 0 6px yellow,
    0 0 0 8px green,
    0 0 0 10px cyan;
}
</style>

---

#### loading效果

通过内阴影和动画制造loading效果

```css
.loading {
    box-shadow: inset 0.5em -0.5em crimson;
    ...
}

```

<iframe height="300" style="width: 100%;" scrolling="no" title="Crimson Crescent Loading" src="https://codepen.io/Chokcoco/embed/eYpxjdp?default-tab=&editable=true" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/Chokcoco/pen/eYpxjdp">
  Crimson Crescent Loading</a> by Chokcoco (<a href="https://codepen.io/Chokcoco">@Chokcoco</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

---

#### 投影阴影

灯光照射效果, css的阴影无法实现。这时可以用transform模仿阴影


<div class="bgLongShadow" w-50 h-50></div>

<style>
.bgLongShadow::before {
    transform-origin: 0 50%;
    transform: translate(100%, 0) skewY(45deg) scaleX(.3);
    background: linear-gradient(90deg, rgba(223, 123, 123, .3), transparent);
    animation: shadowMoveY 5s infinite linear alternate;
}
.bgLongShadow::after {
    transform-origin: 0 0;
    transform: translate(0%, 100%) skewX(45deg) scaleY(.3);
    background: linear-gradient(180deg, rgba(223, 123, 123, .3), transparent);
    animation: shadowMoveX 5s infinite linear alternate;
}
.bgLongShadow::before, .bgLongShadow::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: -1;
}
.bgLongShadow {
    position: relative;
    background: rgba(223, 123, 123, .1);
    margin: 20px auto!important;
    background-size: contain;
    background-position: center;
    background-repeat: no-repeat;
}
</style>

---

#### 阴影按钮

- 立体: 通过阴影加transform结合

<div class="bgSolidShadow"></div>
<div class="bgSolidShadow2"></div>

- 浮雕: 点击时使shadow内嵌

<div class="g-button-relief">浮雕阴影</div>

<style>
div.bgSolidShadow:hover, div.bgSolidShadow2:hover {
    background: transparent;
}
 div.bgSolidShadow, div.bgSolidShadow2 {
    position: relative;
    width: 300px;
    height: 50px;
    margin: 30px auto;
    background: hsl(48, 100%, 50%);
    border-radius: 20px;
    box-shadow: 0 0 3px 1px hsl(48, 100%, 45%);
    cursor: pointer;
}
.bgSolidShadow::before {
    content: "";
    position: absolute;
    top: 40%;
    left: 5%;
    right: 5%;
    bottom: 0;
    border-radius: 10px;
    transform: translate(0, -15%) rotate(-2deg);
    transform-origin: center center;
    box-shadow: 0 0 10px 12px hsl(0, 0%, 0%);
    z-index: -1;
}
div.bgSolidShadow2 {
    background: hsl(199, 98%, 48%);
    box-shadow: 0 0 3px 1px hsl(199, 98%, 40%);
}

.bgSolidShadow2::before {
    content: "";
    position: absolute;
    top: 50%;
    left: 5%;
    right: 5%;
    bottom: 15%;
    border-radius: 10px;
    transform: translate(0, -20%) rotate(-5deg);
    transform-origin: center center;
    box-shadow: 0 0 12px 12px hsl(0, 0%, 0%);
    z-index: -1;
}
.bgSolidShadow2::after {
    content: "";
    position: absolute;
    top: 50%;
    left: 5%;
    right: 5%;
    bottom: 15%;
    border-radius: 10px;
    transform: translate(0, -20%) rotate(5deg);
    transform-origin: center center;
    box-shadow: 0 0 12px 12px hsl(0, 0%, 0%);
    z-index: -1;
}


.g-button-relief.g-button-relief {
    width: 300px;
    height: 100px;
    line-height: 100px;
    margin: auto;
    margin-top: 60px;
    text-align: center;
    border-radius: 20px;
    font-size: 54px;
    text-align: center;
    box-shadow: 5px 5px 9px rgb(0 0 0 / 40%), -5px -5px 9px rgb(58 127 181);
    cursor: pointer;
    user-select: none;
    transition: .2s all;
    color: #2b5e87;
    background: #2b5e87;
    text-shadow: 1.5px 1.5px 1.5px #000, -1.5px -1.5px 1.5px #fff;
}

.g-button-relief:active {
    box-shadow: 0 0 0 rgb(0 0 0 / 40%), 0 0 0 rgb(58 127 181), inset -5px -5px 9px rgb(58 127 181), inset 5px 5px 9px rgb(0 0 0 / 40%);
    text-shadow: 1.5px 1.5px 1.5px #fff, -1.5px -1.5px 1.5px #000;
}
</style>