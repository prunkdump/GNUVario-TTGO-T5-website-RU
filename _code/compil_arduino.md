---
step: 4
description: Компиляция с помощью Arduino IDE 
---

Компилирование кода
-----------------
Предварительно необходимо запустить вариометр без SD-карты, а **затем** подключить его к ПК через разъем USB. Он будет распознан ПК как последовательный порт COMx (пример: COM4).

Теперь запустите Arduino IDE и откройте скетч, который хотите скомпилировать. Например, **Gnuvario-E.ino**.

![GitHub download zip]({{"/assets/code_img/code5.jpg" | absolute_url}})

В меню **Tools** убедитесь, что вы **выбрали правильную плату**. Самый классический для этого проекта - **ESP32 Dev Module**.

и выберите схему разделов: **Minimal SPIFFS (1.9 MB APP with OTA / 180 KB SPIFFS)**

По-прежнему в меню **Tools** выберите последовательный порт, соответствующий вариометру.

![GitHub download zip]({{"/assets/code_img/ide1.jpg" | absolute_url}})

Теперь вы должны выбрать вашу комбинацию экрана и печатной платы. Для этого откройте файл **HardwareConfig.h**, расположенный в папке **Arduino\librairies\HardwareConfig**, с помощью текстового редактора, например [**Notepadd++**](https://notepad-plus-plus.org/downloads/).

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

Сохраните и вернитесь в **IDE Arduino**.

Теперь все, что вам нужно сделать, это просто нажмать кнопку **upload**.

![GitHub download zip]({{"/assets/code_img/code7.jpg" | absolute_url}})

Это запустит компиляцию кода, а затем обновит варио; вариометр перезапустится самостоятельно в конце процедуры.

Теперь вы можете отключить USB, выключить вариометр, вставить SD-карту и запустить его снова.

Чтобы подготовить microSD карту [**Читайте здесь**]({{site.baseurl}}/manuel/SDupdate.html)