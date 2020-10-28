---
step: 2
title: 3D Корпус
description: Нижняя крышка
---

[FFF profil скачать]({{ 'assets/fichiers/profils3Dprinter/Geeetech_A20M_boitier_bas.fff' | relative_url }})

После того, как ваш файл будет загружен в simpleify3d, вы сможете изменить настройки профиля для оптимизации печати.


{% include slicerimg.md name="Bottom_1.jpg" %}


**Вкладка "Extruder":** 


The distance and speed of retraction будут зависеть от вашего принтера. The vertical retraction elevator позволяет немного приподнять сопло таким образом, чтоб избежать касания детали во время движения.


{% include slicerimg.md name="Bottom 2.jpg" %}

**Вкладка "Layer":**

Для этой детали слои 0,2 мм - хороший компромисс между скоростью и качеством печати. При высоте первого слоя 150% первый слой будет 0,3 мм. Скорость 20% по сравнению с общей скоростью печати обеспечивает хорошее сцепление.


{% include slicerimg.md name="Bottom 3.jpg" %}

**Вкладка "Additions":**

Добавьте skirt вокруг корпуса, просто чтобы продуть сопло.


{% include slicerimg.md name="Bottom 4.jpg" %}

**Вкладка "Infill":**

Выберете 40% заполнение сотами (honeycomb).


{% include slicerimg.md name="Bottom 5.jpg" %}

**Вкладка "Support":**

На этой вкладке можно все отключить. Так как поддержки тут не нужны.

{% include slicerimg.md name="Bottom 6.jpg" %}

**Вкладка "Temperature":**

Здесь вы устанавливаете температуру сопла для PLA (Shared Heater, здесь 215 °C) и температуру стола (Heated Bed, здесь 60 °C).


{% include slicerimg.md name="Bottom 7.jpg" %}

**Вкладка "Cooling":**

Для PLA оставьте значения по умолчанию: первый слой без вентилятора, следующий слой, вентилятор на 100%.


{% include slicerimg.md name="Bottom 8.jpg" %}

**Вкладка "G-Code":**

Если вы хотите использовать загружаемый профиль вверху страницы, вы можете здесь изменить характеристики вашего принтера (Cartesian, delta, printing volume, итд.)


{% include slicerimg.md name="Bottom 9.jpg" %}

**Вкладка "Scripts":**

Оставьте скрипты вашего принтера по умолчанию.


{% include slicerimg.md name="Bottom 10.jpg" %}

**Вкладка "Speeds":**

Скорость печати зависит от качества вашего принтера. На 60мм/с проблем быть не должно.


{% include slicerimg.md name="Bottom 11.jpg" %}

**Вкладка "Other":**

Установите диаметр вашего филамента, цену, плотность….


{% include slicerimg.md name="Bottom 12.jpg" %}

**Вкладка "Advenced":**

Thin wall behavior: оставьте "Perimeter only" и "Allow filling of spaces".

{% include slicerimg.md name="Bottom 13.jpg" %}


