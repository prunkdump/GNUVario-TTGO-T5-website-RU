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

Теперь вы должны выбрать вашу комбинацию экрана и печатной платы. Для этого откройте файл **HardwareConfig.h**, расположенный в папке **src\HardwareConfig**.

Выбор комбинации производится раскомментированием строки, соответствующей вашей комбинации. В примере версия 293.

{% highlight shell_session %}
//VERSION
//#define VARIOVERSION 154     //PCB Version 1 avec ecran 1.54 / PCB version 1 with 1.54" screen
//#define VARIOVERSION 254     //PCB Version 2 avec ecran 1.54 / PCB Version 2 with 1.54" screen
//#define VARIOVERSION 290     //PCB Version 2 avec ecran 2.9" paysage / PCB version 2 with 2.9" screen landscape (TTGO-T5-V2.4 before 12/2020)
//#define VARIOVERSION 291     //PCB Version 2 avec ecran 2.9" portrait / PCB version 2 with 2.9" screen portrait (TTGO-T5-V2.4 before 12/2020)
//#define VARIOVERSION 292     //PCB Version 2 avec ecran 2.9" paysage /PCB version 2 with 2.9" screen landscape  (Ecran/Screen Good Display GDEW029M06)      
#define VARIOVERSION 293     //PCB Version 2 avec ecran 2.9" portrait / PCB version 2 with 2.9" screen portrait (Ecran/Screen Good Display GDEW029M06)
//#define VARIOVERSION 294     //PCB Version 2 avec ecran 2.9" portrait / PCB version 2 with 2.9" screen portrait (TTGO-T5-V2.4 after 12/2020 Screen number DKEG0290BNS800F6 /QYEG0290BNS800F6C02 ) For test purpose only
//#define VARIOVERSION 354     //PCB Version 3.1 avec ecran 1.54 / PCB Version 3.1 with 1.54" screen
//#define VARIOVERSION 390     //PCB Version 3.1 avec ecran 2.9" paysage / PCB version 3.1 with 2.9" screen landscape (TTGO-T5-V2.4 before 12/2021)
//#define VARIOVERSION 391     //PCB Version 3.1 avec ecran 2.9" portrait / PCB version 3.1 with 2.9" screen portrait (TTGO-T5-V2.4 before 12/2021)
//#define VARIOVERSION 392     //PCB Version 3.1 avec ecran 2.9" Good Display GDEW029M06 paysage / PCB version 3.1 with 2.9" screen landscape  (Ecran/Screen Good Display GDEW029M06) 
//#define VARIOVERSION 393	   //PCB Version 3.1 avec ecran 2.9" Good Display GDEW029M06 portrait / PCB version 3.1 with 2.9" screen portrait (Ecran/Screen Good Display GDEW029M06) 
//#define VARIOVERSION 395     //PCB Version 3.5 avec ecran 2.9" paysage (futur BNO085/86)
//#define VARIOVERSION 396     //PCB Version 3.5 avec ecran 2.9" portrait (futurBNO085/86)
{% endhighlight %}

А теперь, если вы хотите скомпилировать код и загрузить его в вариометр, вам необходимо:
- включить вариометр
- подключите вариометр к PC через micro USB
- нажмите значек PlatformIO: Upload

Произойдет rомпиляция и если ошибок нет, скомпилированный код будет загружен в вариометр и затем он перезапустится.

Чтобы подготовить microSD карту [**Читайте здесь**]({{site.baseurl}}/manuel/SDupdate.html)