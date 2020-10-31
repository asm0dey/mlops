---
marp: true
theme: gaia
size: 4K
class: default
paginate: true
footer: @asm0di0 @SmartDataCon
backgroundImage: "linear-gradient(to bottom, #000 0%, #1a2028 50%, #293845 100%)"
color: white
title: MLOps
---
<!--
_class: lead
_paginate: false
_footer: ""
-->

<style>
footer {
    display: table
}
.hljs-variable { color: lightblue }
.hljs-string { color: lightgreen }
.hljs-params { color: lightpink }
</style>

# ML: страх и ненависть в продакшне

### Паша Финкельштейн, JetBrains
### Михаил Марюфич, ОК

---

# О себе

- 14 лет в IT
- 11 в разработке с разных концов
- 2 года в DE
- Из них год в [Big Data Tools](https://plugins.jetbrains.com/plugin/12494-big-data-tools) *

![bg right:30% fit](https://plugins.jetbrains.com/files/12494/95821/icon/pluginIcon.svg)


*_Big Data Tools — инструмент для упрощения жизни дата инжинеров_

---

# Михаил Марюфич


Describe here

---

<!-- _class: lead -->

<style scoped>
p:nth-child(2) {
    text-align: right
}
</style>

![bg right fi](https://math-cs.spbu.ru/wp-content/uploads/2019/10/Bragilevskij-V._2019-400x400.jpg)

> MLOps — это не человек, это практики, основанные на технологиях


Эйнштейн

---
<style scoped>
p:nth-child(2) {
    text-align: right
}
</style>

<!-- _class: lead -->

# Цитатам в интернете всегда можно верить

Особенно от Эйнштейна

---
# <!-- fit --> О древнейшей истории

* Буча началась с гиганта
* И гигантом был Google

https://papers.nips.cc/paper/5656-hidden-technical-debt-in-machine-learning-systems.pdf

---

<!-- 
_backgroundImage: "linear-gradient(to bottom, #000 0%, #1a2028 50%, #000 100%)"
 -->
![bg fit invert brightness](images/debt.png)

---
<style scoped>
p:nth-child(2) {
    text-align: right
}
</style>

<!-- _class: lead -->
> # Мы все неправы!

_**Google**_

Потому что не продуктивизируем свой ML код.

---

![bg](images/devops.jpg)

---

# DevOps для обычной разработки

Тем временем в обычной разработке
* Инструментов тонна
* Все знают, как продуктизировать разработку
* Все понимают, где светлое будущее

И конечно же вокруг этого навёрнута тонна практик

---
<!-- _class: lead -->
![bg left:45%](https://images.manning.com/book/8/5753b1d-f666-47c4-bddf-189f09d3676f/Smith-OAP-HI.png)

> DevOps isn’t about tools, but about how teams work together
## Новая книга про анти-паттерны Ops и решения DevOps

---
<!-- _class: lead -->

### <!-- fit --> Так что, MLOps — это просто DevOps?

# **Нет!**

---

![bg](https://content.altexsoft.com/media/2020/07/word-image-3.png)

---

<!-- _class: lead -->
# MLOps — это ещё одна ступень специализации

---

# Как устроен ML

![width:1120px ](https://martinfowler.com/articles/cd4ml/ml-axis-of-change.png)