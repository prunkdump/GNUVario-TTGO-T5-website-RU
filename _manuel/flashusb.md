---
step: 3
title: Руководство
description: Первый запуск
---

Прежде чем вы сможете использовать Gnuvario-E, вы должны установить программное обеспечение и подготовить SD-карту.

### Подготовка SD карты #
На пустую карту MicroSD, отформатированную в Fat16 или 32, скопируйте содержимое папки RootSD в корень SD карты.

### Обновление Gnuvario-E #
Перед обновлением вариометра вы должны загрузить и установить flash download tools с официального сайта.

Flash Download Tools: <https://www.espressif.com/en/support/download/other-tools>

Включите Gnuvario-E без SD-карты; **затем** подключите его к ПК через порт USB. ПК увидит вариометр как последовательный порт; например, COM3.

Запустите flash_download_tools.exe; выберите «ESP32 DownloadTool».

Затем выберите последний .bin файл, используя следующие параметры (выберите COM-порт, соответствующий вариометру):

![Flash_download_tools]({{'/assets/manuel_img/flashTools.jpg' | relative_url}})

Нажмите кнопку «Start»; зеленый квадрат «IDLE» указывает на «Загрузку», а в нижней части отображается зеленый индикатор выполнения. Прошивка программы занимает около 2 минут; Когда закончится, в зеленом квадрате отобразится «FINISH».

Затем вы можете отключить питание Gnuvario-E, отсоединить USB-порт, вставить SD-карту и включить вариометр.