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

# Это доклад о том, что такое MLOps, зачем он нужен и как можно попробовать его делать

Концепции общие, инструменты меняются

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

![h:480 shadow](https://martinfowler.com/articles/cd4ml/ml-axis-of-change.png)

---

<!-- _class: lead -->

### И всё это один большой кусок кода!

---

![bg left:30%](https://source.unsplash.com/h9Rx3zOYZws)


# А кто такие дата саентисты?

* Data — данные, тут всё понятно.
  * копаются в реке и находят золото
* Scientists — учённые. Экспериментаторы

---

![bg brightness:30%](https://source.unsplash.com/JeInkKlI2Po)

# Требования к эксперименту

* Формулирование гипотезы
* Описание специфических условий
* Воспроизводимость
* Протоколирование

---

<!-- _class: lead -->

<style scoped>
p:nth-child(2) {
    text-align: right
}
</style>

![bg right:40%](https://math-cs.spbu.ru/wp-content/uploads/2019/10/Bragilevskij-V._2019-400x400.jpg)

> MLOps — это это способ сделать эксперименты научным, а не наколеночным


Эйнштейн

---
<style scoped>
p:nth-child(2) {
    text-align: right
}
</style>

# Я всегда верю цитатам в интернете

![bg brightness:60%](https://source.unsplash.com/8recjlHwCWA)

Курт Кобейн

---

# Как устроен ML

![width:1120px ](https://martinfowler.com/articles/cd4ml/ml-axis-of-change.png)

---

# Что тут пошло не так?

* Всё одним куском
* Протокола эксперимента нет
* Информации об исходных данных нет
* Результаты меняются от запуска к запуску

---

<!-- 
_class: invert 
_color: #000000
-->

# Что делать?

![bg w:1300](https://martinfowler.com/articles/cd4ml/ml-pipeline-1.png)

---
![bg fit](images/dvc.png)