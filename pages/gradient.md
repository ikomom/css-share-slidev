---
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# 渐变

gradient

<v-clicks>

<div>
1. 线性渐变 linear-gradient

<p bg-gradient-to-r from-green-500 w-50 h-10>
</p>
</div>

<div>
2. 径向渐变 radial-gradient
<p w-50 h-20 class="radius">
</p>
</div>

<div>
3. 多重阴影 conic-gradient

<p w-50 h-20 class="conic">
</p>
</div>

</v-clicks>

<style>
.radius {
    background: radial-gradient(#e66465, #9198e5);
}
.conic {
    background: conic-gradient(deeppink, yellowgreen);
}
</style>

---
class: bg-blue-500/50
---

# 线性渐变


<div>

- 快速实现pk效果
```css
background: linear-gradient(45deg, #fff 50%, #ffcc00 50%);
```
<div class="g-linear-gradient-2"></div>

</div>

<v-clicks>

<div>

- 某一段的颜色可以是透明的
```css
background: linear-gradient(45deg, #fff 33%,  transparent 33%, transparent 66%,  #ffcc00 66% );
```
<div class="g-linear-gradient-3"></div>
</div>

<div>

- 斑马线效果

```css
background: repeating-linear-gradient(45deg, #ffcc00, #ffcc00 10px, transparent 10px, transparent 19px, #ffcc00 20px);
```

<div>
    <div class="g-linear-gradient-4"></div>
    <div class="g-linear-gradient-6" overflow-hidden></div>
</div>
</div>

</v-clicks>

<style>
.g-linear-gradient-2 {
    margin: 20px auto!important;
    width: 400px;
    height: 30px;
    background: linear-gradient(45deg, #e10b84 50%, #0015ff 50%);
}
.g-linear-gradient-3 {
    margin: 20px auto!important;
    width: 400px;
    height: 30px;
    background: linear-gradient(45deg, #e10b84 33%, transparent 33%, transparent 66%, #0015ff 66%);
}

.g-linear-gradient-4 {
    margin: 20px auto!important;
    width: 400px;
    height: 30px;
    background: repeating-linear-gradient(45deg, #ffcc00, #ffcc00 10px, transparent 11px, transparent 19px, #ffcc00 20px);
}
.g-linear-gradient-6 {
    position: relative;
    width: 400px;
    height: 30px;
    margin: auto;
}

.g-linear-gradient-6::before {
    position: absolute;
    content: "";
    top: 0;
    left: 0;
    width: 400px;
    height: 85px;
    background: repeating-linear-gradient(45deg, #ffcc00, #ffcc00 10px, transparent 11px, transparent 19px, #ffcc00 20px);
    background-position: 0 0;
    background-repeat: no-repeat;
    animation: barMove 1s linear infinite;
}
@keyframes barMove {
    from { background-position: 0 0; }
    to { background-position: 0 -56px; }
}


</style>

---

# 优惠券

background + 径向渐变

```css
{
    background-image: 
        radial-gradient(circle at 1px 8px, transparent 6px, #ffcc00 6px, #ffcc00 0px),
        radial-gradient(circle at 199px 8px, transparent 6px, #ffcc00 6px, #ffcc00 0px);
    background-size: 200px 18px;
    background-position: 0 0, 200px 0;
    background-repeat-x: no-repeat;
}
```
<div class="g-linear-gradient-8">50</div>

<style>
div.g-linear-gradient-8 {
    position: relative;
    width: 400px;
    height: 160px;
    margin: 50px auto!important;
    background-image: radial-gradient(circle at 1px 8px, transparent 6px, #ffcc00 6px, #ffcc00 0px), radial-gradient(circle at 199px 8px, transparent 6px, #ffcc00 6px, #ffcc00 0px);
    background-size: 200px 18px;
    background-position: 0 0, 201px 0;
    background-repeat-x: no-repeat;
    font-size: 100px;
    color: #fff;
    font-weight: bold;
    line-height: 160px;
    padding-left: 60px;
    box-sizing: border-box;
    cursor: pointer;
    text-align: initial;
}
.g-linear-gradient-8::before {
    position: absolute;
    content: "";
    left: 240px;
    top: 0;
    bottom: 0;
    width: 0;
    border-left: 2px dashed rgb(12, 9, 46);
}
.g-linear-gradient-8::after {
    position: absolute;
    content: "立即领取";
    font-size: 30px;
    width: 70px;
    top: 50%;
    right: 2%;
    transform: translate(-50%, -50%);
    line-height: 40px;
    letter-spacing: 5px;
}
</style>

---

# 各种渐变例子

- 文字波浪线

<div grid grid-cols-2>
    <div class="gradient-wave">渐变实现波浪</div>
    <div class="flow-wave">Hover Me</div>
</div>

<v-clicks>

<div>

- 调色盘

```css
    background: conic-gradient(
        red, #ff4d00, #ff9900, #ffe600, #ccff00, #80ff00, #33ff00, #00ff1a, #00ff66, #00ffb3,
        cyan, #00b3ff, #0066ff, #001aff, #3300ff, #8000ff, #cc00ff, #ff00e6, #ff0099, #ff004d, 
        red
    );
```
    <div class="g-conic-2"></div>
</div>

</v-clicks>

<style>

div.gradient-wave {
    position: relative;
    margin: 30px auto;
    height: 24px;
    font-size: 14px;
    text-decoration: none;
    cursor: pointer;
    transform: scale(3);
}

.gradient-wave::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: radial-gradient(circle at 10px -7px, transparent 8px, deeppink 8px, deeppink 9px, transparent 9px) repeat-x;
    background-size: 20px 20px;
    background-position: -10px calc(100% + 16px);
}
.gradient-wave::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: radial-gradient(circle at 10px 27px, transparent 8px, #ffcc00 8px, #ffcc00 9px, transparent 9px) repeat-x;
    background-size: 20px 20px;
    background-position: 0 calc(100% - 4px);
}
.gradient-wave:hover::before {
    animation: moveTop 2s infinite alternate linear;
}
.gradient-wave:hover::after {
    animation: moveBottom 2s infinite alternate linear;
}

@keyframes moveTop {
    100% {
        bottom: -5px;
    }
}

@keyframes moveBottom {
    100% {
        bottom: 5px;
    }
}

.flow-wave {
    height: 26px;
    font-size: 16px;
    transform: scale(3);
    text-decoration: none;
    margin: 20px auto;
    background: radial-gradient(circle at 10px -7px, transparent 8px, currentColor 8px, currentColor 9px, transparent 9px) repeat-x, radial-gradient(circle at 10px 27px, transparent 8px, currentColor 8px, currentColor 9px, transparent 9px) repeat-x;
    background-size: 20px 20px;
    background-position: -10px calc(100% + 16px), 0 calc(100% - 4px);
}
.flow-wave:hover, .flow-wave:focus {
    background: radial-gradient(circle at 10px -7px, transparent 8px, currentColor 8px, currentColor 9px, transparent 9px) repeat-x, radial-gradient(circle at 10px 27px, transparent 8px, currentColor 8px, currentColor 9px, transparent 9px) repeat-x;
    background-size: 20px 20px;
    background-position: -10px calc(100% + 16px), 0 calc(100% - 4px);
    animation: waveFlow 1s infinite linear;
}
@keyframes waveFlow {
    0% {
        background-position-x: -10px, 0;
    }
    
    100% {
        background-position-x: -30px, -20px;
    }
}
.g-conic-2 {
    width: 160px;
    height: 160px;
    margin: 20px auto;
    background: conic-gradient(red, #ff4d00, #ff9900, #ffe600, #ccff00, #80ff00, #33ff00, #00ff1a, #00ff66, #00ffb3, cyan, #00b3ff, #0066ff, #001aff, #3300ff, #8000ff, #cc00ff, #ff00e6, #ff0099, #ff004d, red);
    border-radius: 50%;
}
</style>

---

# 积分表盘

<iframe src="https://codepen.io/alphardex/embed/BaydVvQ?height=320&theme-id=1&default-tab=result&editable=true" height="450" width="100%"/>

---

# 利用角向渐变实现边框效果

<iframe src="https://codepen.io/Chokcoco/embed/YzGdEMZ?default-tab=result&editable=true" height="450" width="100%"/>

---
layout: iframe

# the web page source
url: https://codepen.io/Chokcoco/embed/dypaobm?default-tab=result&editable=true
---
