---
step: 4
title: Руководство
description: Wifi
---

В Gnuvario-E есть веб-сервер, который позволит вам настраивать Gnuvario, обновлять его, копировать файлы полетов, а также копировать файлы на SDCard.
 
{% include manuelimg.md name = "ecran291wifireboot.png"%}

**Настройки WiFi**

Прежде чем вы сможете использовать Wi-Fi с Gnuvario-E, вы должны указать SSID и пароль вашего роутера или телефона.

Заполните информацию в файле wifi.cfg. Вы можете указать до 4 различных сетей Wi-Fi.

Если вы не хотите использовать SD-карту, вам нужно будет заполнить файл variosettings.h (требуется компиляция кода).


#define DEFAULT_VARIOMETER_SSID_1													"your_SSID1"   
#define DEFAULT_VARIOMETER_PASSWORD_1											"your_PASSWORD_for SSID1"   

#define DEFAULT_VARIOMETER_SSID_2													"your_SSID2"   
#define DEFAULT_VARIOMETER_PASSWORD_2											"your_PASSWORD_for SSID2"   

#define DEFAULT_VARIOMETER_SSID_3													"your_SSID3"   
#define DEFAULT_VARIOMETER_PASSWORD_3											"your_PASSWORD_for SSID3"   

#define DEFAULT_VARIOMETER_SSID_4													"your_SSID4"   
#define DEFAULT_VARIOMETER_PASSWORD_4											"your_PASSWORD_for SSID4"   

**Переключение в режим Wifi**

При запуске нажмите левую кнопку

Как только Gnuvario-E подключается к сети Wi-Fi, на экране отображается адрес веб-страницы:



**Подключение к веб-странице**

Запустите свой веб-браузер и перейдите по указанному IP-адресу.




