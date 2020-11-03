---
step: 1
description: Arduino IDE
---

Чтобы скомпилировать исходный код GNUVario-E, вам понадобится IDE Arduino [скачать здесь](https://www.arduino.cc/en/Main/Software). Начните с его установки и убедитесь, что вы можете запустить редактор.

Далее нужно добавть библиотеки ESP32 в Arduino IDE. Для этого:

Перейдите на вкладку **"File"**, затем **"Preferences"** среды IDE и добавьте URL-адрес **https://dl.espressif.com/dl/package_esp32_index.json** к URL-адресам дополнительных плат.

![GitHub zip download]({{"/assets/code_img/code11.jpg" | absolute_url}})

Затем перейдите на кладку **"Tools"**, **"Board"** и выберите **"Boards manager"**

![GitHub zip download]({{"/assets/code_img/code12.jpg" | absolute_url}})

Найдите **ESP32 by Espressif Systems** и установите 
Look for the  cards then click on install.

![GitHub zip download]({{"/assets/code_img/code13.jpg" | absolute_url}})

Теперь когда IDE настроена, вы можете скачивать исходный код GNUVario-E.
