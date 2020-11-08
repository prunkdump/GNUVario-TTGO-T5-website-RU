---
description: Ошибка компиляции кода в Arduino IDE
---

- Папка Arduino по умолчанию (под Windows **Documents/Arduino**) должна содержать только файлы проекта Gnuvario; по сути, два файла:
   - *Gnuvario-E*: содержит Gnuvario-E.ino
   - *libraries*:: библиотеки проекта и только они.
- Вы должны включить вариометр и без SD-карты, прежде чем подключать его к ПК через USB.
- В меню *Tools* Arduino IDE выбрана плата *ESP32 Dev Module*, схема разделов *Minimal SPIFFS (1.9 MB APP with OTA / 180 KB SPIFFS)* и COM-порт, соответствующий vario .


См. [специальную документацию]({{ site.baseurl }}/5-code.html)