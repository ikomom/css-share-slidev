# 滤镜

<iframe height="450" style="width: 100%;" scrolling="no" title="CSS3 filter (cancle filter by hover)" src="https://codepen.io/Chokcoco/embed/wrwbvG?default-tab=&editable=true" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/Chokcoco/pen/wrwbvG">
  CSS3 filter (cancle filter by hover)</a> by Chokcoco (<a href="https://codepen.io/Chokcoco">@Chokcoco</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

---

滤镜可以叠加；
多个滤镜叠加，顺序不同，效果不同

```css
{
    filter: blur(5px);
    filter: brightness(0.4);
    filter: contrast(200%);
    filter: drop-shadow(16px 16px 20px blue);
    ...

    /* Apply multiple filters */
    filter: contrast(175%) brightness(3%);
}
```

---

# 增亮图片

```css
:hover {
    filter: brightness(1.1) contrast(110%);
}
```

<iframe height="300" class="mt-10" style="width: 100%;" scrolling="no" title="CSS3 filter hover IMG" src="https://codepen.io/Chokcoco/embed/RLwbyr?default-tab=&editable=true" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/Chokcoco/pen/RLwbyr">
  CSS3 filter hover IMG</a> by Chokcoco (<a href="https://codepen.io/Chokcoco">@Chokcoco</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

---
class: bg-black
---


# 滤镜融合

<div class="g-mix">
    <div class="ball"></div>
    <div class="box"></div>
</div>

<style>
div.g-mix {
    position: relative;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    filter: contrast(15);
    background: #000;
}
.ball {
    position: absolute;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    background-color: #ff3c41;
    filter: blur(8px);
}
.box {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) rotate(0);
    background-color: #ff3c41;
    border-radius: 50%;
    width: 100px;
    height: 100px;
    animation: turn 5s linear infinite;
    transform-origin: -100% center;
    filter: blur(8px);
}

@keyframes turn {
    100% {
        transform: translate(-50%, -50%) rotate(360deg);
    }
}
</style>

---
layout: iframe

# the web page source
url: https://codepen.io/Chokcoco/embed/BaaQEab?default-tab=&editable=true
---

---
layout: iframe

# the web page source
url: https://codepen.io/Chokcoco/embed/jJJbmz?default-tab=&editable=true
---
