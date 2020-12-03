---
marp: true
theme: gaia
size: 4K
class: default
paginate: true
footer: @asm0di0 @mikhailmar @SmartDataCon
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
### Михаил Марюфич, OK.ru

---

# О себе

- 14 лет в IT
- 11 в разработке с разных концов
- 2 года в DE
- Из них год в [Big Data Tools](https://plugins.jetbrains.com/plugin/12494-big-data-tools) *

![bg right:30% fit](https://plugins.jetbrains.com/files/12494/95821/icon/pluginIcon.svg)


*_Big Data Tools — инструмент для упрощения жизни дата инженеров_

---

# Михаил Марюфич


 - Закончил Мат-Мех СПбГУ и Computer Science Center

- Machine Learning Engineer в OK.ru

- Делаю МЛ штуки и внедряю их в продакшен

- Увлекаюсь воспроизводимостью

 

 ![bg right:30% fit](images/ok.png)

 
---

<!-- _class: lead -->

# Это доклад о том, что такое MLOps, зачем он нужен и как можно попробовать его делать

Концепции общие, инструменты меняются

---
# <!-- fit --> О древнейшей истории

- Буча началась с гиганта
- И гигантом был Google

https://papers.nips.cc/paper/5656-hidden-technical-debt-in-machine-learning-systems.pdf


---
![bg fit invert](https://www.7wdata.be/wp-content/uploads/2020/08/machine-learning1.png)

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
- Инструментов тонна
- Все знают, как продуктизировать разработку
- Все понимают, где светлое будущее

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

![bg left:30%](https://source.unsplash.com/h9Rx3zOYZws)


# А кто такие дата саентисты?

- Data — данные, тут всё понятно.
  - копаются в реке и находят золото
- Scientists — учёные. Экспериментаторы

---
Роли в ML разработке

<!-- 
_backgroundImage: "linear-gradient(to bottom, #000 0%, #1a2028 50%, #000 100%)"
 -->

![bg width:870px](images/ds_roles.png)

---


![bg brightness:30%](https://source.unsplash.com/JeInkKlI2Po)

# Требования к эксперименту

- Формулирование гипотезы
- Описание специфических условий
- Воспроизводимость
- Протоколирование

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
###  ML workflow
![bg width:900px](images/pipe.png)

---
## А чем ПРИНЦИПИАЛЬНО отличается от DEVOPS?

![bg center width:800](https://devopedia.org/images/article/54/7602.1513404277.png)

---
![bg fit](images/pipe1.png)

---
### Это же билд!
![bg fit](images/pipe1.png)

---
### Это же билд!
![bg fit](images/pipe1.png)

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
PS: только очень сложный

--- 
# Что тут пошло не так?

- Всё одним куском
- Протокола эксперимента нет
- Информации об исходных данных нет
- Результаты меняются от запуска к запуску

---

<!-- 
_class: invert 
_color: #000000
-->

# Что делать?

![bg w:1300](https://martinfowler.com/articles/cd4ml/ml-pipeline-1.png)

---
<!-- _class: lead -->
# <!-- fit --> Разве это не очевидно?
# НЕТ!

---

<!-- _color: black -->

# Jupyter

![bg fit](https://user-images.githubusercontent.com/5924038/45263346-5e666980-b430-11e8-822b-e863c8f23686.png)

---

# Jupyter

- Самый популярный (и достаточно удобный) инструмент Data Scientist'а
- Код вперемешку с Markdown
- Написан и исполняется в непредсказуемом порядке

![bg fit brightness:30%](https://user-images.githubusercontent.com/5924038/45263346-5e666980-b430-11e8-822b-e863c8f23686.png)

---
<!-- _class: lead -->
# <!-- fit --> Придётся переучивать

---
![bg fit](images/dvc.png)

---

# DVC

- Создавался специально в пару к гиту
- Изначально был похож на LFS (git-lfs)
- Оброс функциональностью

---

# Примеры

```bash
git add
dvc add
```

Добавить какой-то файл под контроль git/dvc

---

# Примеры
```bash
git commit
dvc commit
```

Сохранить состояние файла

---

# Примеры
```bash
git diff
dvc diff
```

Посмотреть разницу с каким-то состоянием

---

![bg fit](images/pipe1.png)

---
<!-- _class: lead -->
# <!-- fit --> The talk is cheap

## Show us the demo!

![bg brightness:50%](https://source.unsplash.com/bdBeUfTShtA)

---

# Ок, но это консоль

- Молодёжь :older_man: не любит терминалы
- Этим неудобно пользоваться при командной разработке
- Тимлиду может быть неудобно работать с метриками

![bg right:40%](https://source.unsplash.com/wCIDfKBMDHE)

---
<!-- _color: black -->

# PR - это очень удобно

![bg](images/PR.png)

---

![bg fit drop-shadow](https://mlflow.org/images/MLflow-logo-final-white-TM.png)

---

# Easy

```python
mlflow.sklearn.autolog()
remote_server_uri = "http://127.0.0.1:5000"
mlflow.set_tracking_uri(remote_server_uri)
mlflow.set_experiment("udemy-courses")
```

---

## MLFlow Tracking 

![w:1120](images/mlflow.png)

---

##  MLFlow Tracking  - сравнение запусков

![bg fit ](images/mlflow_compare.png)

---
##  MLFlow Tracking  - сравнение запусков

![w:1120](images/mlflow_plots.png)

---

### MLFLOW MODEL REGISTRY

![bg fit](https://www.mlflow.org/docs/latest/_images/oss_registry_3_overview.png)

---


# Как модель там окажется?

![bg fit](https://www.mlflow.org/docs/latest/_images/oss_registry_2_dialog.png)

---

# Как модель там окажется?

```python
from mlflow.tracking import MlflowClient

client = MlflowClient()
client.create_registered_model("sk-learn-random-forest-reg-model")
```

```python
client = MlflowClient()
result = client.create_model_version(
    name="sk-learn-random-forest-reg-model",
    source="mlruns/0/d16076a3ec534311817565e6527539c0/artifacts/sklearn-model",
    run_id="d16076a3ec534311817565e6527539c0"
)
```

---
# Что дальше?

- У нас есть модельки
- У нас есть каталог моделек
- Тестируем!

---

# Тестируем

Мы уже знаем всё, что надо знать про модельки:

1. Среднеквадратичное отклонение
2. Коэффициент детерминации
3. Метрики, специфичные для нашей модели

Всё это можно делать в целом в любом CI!

---
![bg fit](images/pipe3.png)

---


# Serve 
* Есть ML MODEL - это бинарник (.pkl, .pth, .h5)
* Нужно делать к ней запросы

---
![bg brightness:60%](images/meme.jpg)
# Serve 
- Есть ML MODEL - это бинарник (.pkl, .pth, .h5)
- Нужно делать к ней запросы
- И каждый стремится написать свой велосипед =( 

--- 

# MLFLOW SERVING

![bg 90%](images/mlflow-serve2.png)

--- 

![bg fit](https://raw.githubusercontent.com/SeldonIO/seldon-core/master/doc/source/images/seldon-core-high-level.jpg)

---

## Show us the demo!

![bg brightness:50%](https://source.unsplash.com/bdBeUfTShtA)

--- 

# Мониторинг

2 типа инструментов:
1. ML-Специфичные
2. Общие

---

# MLWatcher


- range, mean, std, median, q25, q50, q75, iqr for any continuous values (probabilities, features)
- count, frequency for any discrete values (labels, classes)

Python-агент, который позволяет мониторить *статистические* метрики

Sampling

---

# Пример

![width:1220](https://raw.githubusercontent.com/anodot/MLWatcher/master/IMAGES/concept_drift.png)

Метрики улетают когда цвета внезапно инвертируются

---

# Использование

1. Уложить MLWatcher рядом со своим приложением :scream:
2. Поднять сервер
3. Начать с определённой частотой репортить метрики на сервер

---

# Общие метрики

Мониторить параметры модели - мало

Надо мониторить
1. Системный метрики
1.1. la
1.2. free
1.3. latency…
2. Бизнес-метрики модели (например потерянные клиенты)

---

# Инструменты

- Prometheus
- Grafana
- Zabbix etc


---

![bg width:1500 height:600](https://docs.seldon.io/projects/seldon-core/en/v1.1.0/_images/dashboard.png)

---

<!-- _class: lead -->
# Мониторинг — важнейшая часть продуктивизированного ML

Без него не имеет смысла вообще продуктивизировать — будет непредсказуемо

---

# Чему мы научились

1. MLOps — это процессы и командное взаимодействие
2. Чтобы построить MLOps надо иметь базовый набор инструментов
3. Кроме стандартных инструментов есть и непривычные: DVC, MLFlow
4. Продуктивизация ML — это большой путь, который надо пройти

---
<!-- 
_class: lead 
_footer: ""
-->
# <!-- fit --> QA

Паша Финкельштейн: if (:bird:) @asm0di0 else @asm0dey
Михаил Марюфич: @mikhailmar
