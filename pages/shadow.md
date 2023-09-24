---
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# 阴影

shadow

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


# 阴影多重边框

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

# 不规则边框

当不规则图形想要添加边框时，可以通过drop-shadow模拟边框和光晕效果

```css
{
    filter: 
        drop-shadow(0px 0px 1px blue)
        drop-shadow(0px 0px 1px blue)
        drop-shadow(0px 0px 1px blue);
}
```
<div flex m-10 gap-10 justify-center items-center>
<div class="g-button-unregular-border"></div>
<div class="g-button-unregular-border spread"></div>
</div>


<style>
.g-button-unregular-border {
    position: relative;
    width: 200px;
    height: 80px;
    filter: drop-shadow(0px 0px 1px blue) drop-shadow(0px 0px 1px blue) drop-shadow(0px 0px 1px blue);
}

.spread {
    filter: drop-shadow(0px 0px 1px blue) drop-shadow(0px 0px 12px yellow) drop-shadow(0px 0px 14px red);
}

.g-button-unregular-border::after {
    content: "";
    position: absolute;
    inset: 0;
    clip-path: polygon(85% 0%, 100% 50%, 85% 100%, 0% 100%, 0% 0%);
    background: #f44336;
}
</style>


---

# loading效果

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

# 投影阴影

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

# 阴影按钮

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

---
class: 'bg-black'
---

# 抖音 LOGO
<p text-white>利用shadow / drop-shadow / filter单标签实现 Logo</p>

<div class="tiktok"></div>

<style>
.bg-black{
    background: #1b1b1b;
}
.tiktok {
    position: relative;
    width: 37px;
    height: 218px;
    margin: 30px auto!important;
    background: #fff;
    filter: drop-shadow(-10px -10px 0 #24f6f0) contrast(150%) brightness(110%);
    box-shadow: 11.6px 10px 0 0 #fe2d52;
    z-index: 10;
    animation: TikTokmove 5s infinite ease-in;
}
.tiktok::before {
    content: "";
    position: absolute;
    width: 160px;
    height: 160px;
    border: 37px solid #fff;
    border-top: 37px solid transparent;
    border-radius: 50%;
    top: 137px;
    left: -123px;
    transform: rotate(45deg);
    filter: drop-shadow(16px 0px 0 #fe2d52);
}

.tiktok::after {
    content: "";
    position: absolute;
    width: 143px;
    height: 140px;
    border: 25px solid transparent;
    border-bottom-color: #fff;
    top: -69px;
    right: -121px;
    border-radius: 100%;
    transform: rotate(45deg);
    z-index: -10;
    filter: drop-shadow(14px 0 0 #fe2d52);
}

@keyframes TikTokmove {
    4% {
        transform: skewX(7deg) translate(-30px);
    }
    
    7% {
        transform: skewX(-6deg) translate(18px);
    }
    9% {
        transform: skewX(5deg) translate(-8px);
    }
    10% {
        transform: skewX(-4deg)translate(6px);
    }
    11% {
        transform: skewX(3deg)translate(-4px);
    }
    12% {
        transform: skewX(-2deg) translate(2px);
    }
    13% {
        transform: skewX(1deg) translate(0px);
        filter: drop-shadow(-10px -10px 0 #24f6f0) contrast(120%) brightness(110%) blur(3px);
    }
    30% {
        filter: drop-shadow(-10px -10px 0 #24f6f0) contrast(150%) brightness(120%) blur(0px);
    }
}
</style>
