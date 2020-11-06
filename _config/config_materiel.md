---
step: 1
description: Аппаратная настройка
---

Эта часть необходима только в том случае, если вы хотите использовать нестандартные комплектующие для сборки GnuVario-E.

Перед настройкой аппаратной части вы должны знать, как [компилировать код]({{site.baseurl}}{% link 5-code.md%}). Убедитесь, что вы знаете среду разработки Arduino IDE.

Конфигурация, связанная с оборудованием, выполняется путем редактирования файлов [libraries/HardwareConfig/HardwareConfig.h](https://github.com/prunkdump/GNUVario-TTGO-T5/tree/master/Sources/Beta%20Code/libraries/HardwareConfig/HardwareConfig.h) и [libraries/HardwareConfig/HardwareConfigESP32.h](https://github.com/prunkdump/GNUVario-TTGO-T5/tree/master/Sources/Beta%20Code/libraries/HardwareConfig/HardwareConfigESP32.h) в папке Arduino. Если у вас нет редактора, подходящего для написания кода, вы можете скачать его [Notepad ++](https://notepad-plus-plus.org/).

Начните с проверки файлов. Есть файл, общий для всех микроконтроллеров, и файл, связанный с ESP32 (TTGO-T5). В этих файлах находится конфигурация **оборудования**, количество контактов, адреса карт или памяти. Каждый вариант задокументирован комментариями прямо в этом файле, внимательно прочтите их.

Чтобы «закомментировать» строку, добавьте в начало «//». Это отключает опцию.

Обычно, если вы используете экран размером, отличным от 1,54", вам нужно только адаптировать тип экрана: это директива **VARIOSCREEN_SIZE** в файле HardwareConfig.h.

