---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Css share
  CSS 创意分享
drawings:
  persist: false
transition: slide-left
title: CSS 创意分享
mdc: true
---

# CSS 创意分享

Orion Ye

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/ikomom/css-share-slidev" target="_blank" alt="GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
---

# 分享内容

常见的css有不常见的用法

- 📝 **布局** - layout
- 🎨 **阴影** - shadow
- 🧑‍💻 **渐变** - gradient
- 🤹 **混合模式** - blend mode

[//]: # (- 🎥 **滤镜** - filter)

[//]: # (- 📤 **SVG 滤镜** - svg filter)

[//]: # (- 🛠 **伪元素** - pseudo element)

[//]: # (- 🌊 **波浪效果** - wave effect)

[//]: # (- 🦼 **滚动视差** - scrolling parallax)

[//]: # (- ✨ **3D**)

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
src: ./pages/layout.md
hide: false
---

---
src: ./pages/shadow.md
hide: false
---

---
src: ./pages/shadow.md
hide: false
---

---
src: ./pages/gradient.md
hide: false
---


---
layout: center
class: text-center
---

# Share End

分享结束, 谢谢观看

[GitHub](https://github.com/slidevjs/slidev) 
