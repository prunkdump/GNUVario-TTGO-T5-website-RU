---
step: 5
description: Компиляция с помощью VSCode - PlatformIO 
---

Предварительно вы должны загрузить исходники локально из репозитория GIT. 
Локальный каталог должен содержать как минимум:
- папку src/, содержащую файл Gnuvario-E.cpp
- папку lib/, содержащую необходимые библиотеки
- файлы platformio.ini и custompart.csv

{% include codeimg.md name="platformio_files.jpg"%}

В VSCode нажмите значок «PlatformIO: Home» на горизонтальной панели внизу. В среде IDE появится домашняя страница PlatformIO.

{% include codeimg.md name="platformio_home.jpg"%}

Нажмите 'Import Arduino Project'.
- выберите плату (board). Чтобы ускорить поиск, введите **esp32**, затем выберите «Expressive ESP32 Dev Module».
- не ставьте галочку 'Use libraries installed by Arduino IDE'
- выберите папку, содержащую скаченный из репозитария git код
- нажмите кнопку 'Import'

{% include codeimg.md name="platformio_import_project.jpg"%}

Проект появится в левом столбце (EXPLORER) IDE; можно посмотреть различные его файлы.

{% include codeimg.md name="platformio_projet.jpg"%}

На нижней горизонтальной панели отображаются несколько значков, связанных с PlatformIO и текущим проектом.
Самые интересные значки:
- (1). PlatformIO: Home: открытие главного окна PlatformIO
- (2). PlatformIO: Build: скомпилировать код
- (3). PlatformIO: Upload: скомпилировать код и загрузить его в вариометр
- (8). Platformio: Serial Monitor: открытие монитора последовательного порта

А теперь, если вы хотите скомпилировать код и загрузить его в вариометр, вам необходимо:
- включить вариометр
- подключите вариометр к PC через micro USB
- нажмите значек PlatformIO: Upload

Компиляция будет сделана, если ошибок нет, скомпилированный код будет загружен в вариометр и затем он перезапустится.
