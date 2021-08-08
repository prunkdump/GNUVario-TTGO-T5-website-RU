---
description: Мой вариометр вылетает случайным образом.
---

Мы выявили несколько ситуаций, приводящих к случайным сбоям вариометра.

**1. Список отладки:**{: style="color:   #138ca2; opacity: 1;" }

Раскомментируйте только строки `#define PROG_DEBUG` и `#define DATA_DEBUG` в файле `Arduino\libraries\VarioLog\DebugConfig.h`

{% highlight shell_session %}
#define ENABLE_DEBUG

#if defined(ENABLE_DEBUG)

//              DEBUGING MODE
#define PROG_DEBUG			  //debug principal program
//#define HARDWARE_DEBUG
//#define IMU_DEBUG			  //debug IMU
//#define CAL_DEBUG
//#define I2CDEV_SERIAL_DEBUG   //debug I2Cdev
//#define DEBUG_SERIAL_NMEA_1
//#define SCREEN_DEBUG
//#define SCREEN_DEBUG2
//#define GPS_DEBUG
//#define BUTTON_DEBUG
//#define TONEDAC_DEBUG
//#define MS5611_DEBUG
//#define KALMAN_DEBUG
//#define ACCEL_DEBUG
//#define EEPROM_DEBUG
//#define NMEAPARSER_DEBUG
//#define SDCARD_DEBUG
//#define IGC_DEBUG
#define DATA_DEBUG
//#define BT_DEBUG
//#define WIFI_DEBUG
//#define SOUND_DEBUG
//#define AGL_DEBUG
//#define SQL_DEBUG
//#define BEARING_DEBUG
//#define TWOWIRESCH_DEBUG
//#define POWER_DEBUG
//#define MEMORY_DEBUG
{% endhighlight %}


**2. Уменьшите скорость шины I2C:**{: style="color:   #138ca2; opacity: 1;" }

Самая распространенная проблема - потеря информации о высоте. Модуль CJMCU-117, в который встроен барометр MS5611, обменивается данными с микросхемой ESP32 по протоколу [I2C](https://fr.wikipedia.org/wiki/I2C).Вы можете попробовать снизить скорость передачи данных по шине с 400 до 100 кГц. Чтобы сделать это, измените значение `400000UL` на `100000UL` в строке 355 файла `Arduino\libraries\HardwareConfig\HardwareConfigESP32.h`  

{% highlight shell_session %}
/* Set the freq */
#define VARIO_TW_FREQ 400000UL

на

/* Set the freq */
#define VARIO_TW_FREQ 100000UL

{% endhighlight %}

**3. Качество пайки:**{: style="color:   #138ca2; opacity: 1;" } 

Часто причиной ошибок является качество пайки, даже если кажется, что все хорошо. Попробуйте прогреть паяльником контакты на печатной плате.
