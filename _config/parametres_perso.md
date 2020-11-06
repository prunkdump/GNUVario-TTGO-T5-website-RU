---
step: 3
description: Список настраиваемых параметров
---

### params.jso #

Это файл в формате json, позволяет настраивать работу GnuVario.

Основные параметры этого файла:

**system - SLEEP_TIMEOUT_MINUTES**

default: 20 минут<br>
переход в режим ожидания через Х минут бездействия

**system - SLEEP_THRESHOLD_CPS**

default: 0.5 м. <br>
порог срабатывания активности (эквивалент +0.5 Vz)

**system - ALARM_SDCARD**

1 = Звуковой сигнал, указывающий на то, что SD-карта отсутствует

**system - ALARM_GPSFIX**

1 = Звуковой сигнал, указывающий, что GPS зафиксировался

**system - ALARM_FLYBEGIN**

1 = Звуковой сигнал, указывающий на начало записи полета

**system - NO_RECORD**

default: 0<br>
1 = отключение записи на SD-карту лога полета

**system - BT_ENABLE**

default: 0<br>
1 = включение Bluetooth

**system - COMPENSATION_TEMP**

default: -6<br>
температурная компенсация

**system - COMPENSATION_GPSALTI**

default: -30<br>
Компенсация высоты GPS

**system - MULTIDISPLAY_DURATION**

default: 2000 milliseconds<br>
Альтернативное время отображения разных страниц (в миллисекундах)

**system - DEFAULT_DISPLAY_STAT_DURATION**

default: 6<br>
Продолжительность в секундах времени отображения страницы «статистика»

**system - URL_UPDATE**

default: http://gnuvario-e.yj.fr/update/firmware.json<br>
Путь к сайту хранилища обновлений

**general - TIME_ZONE**

Определяет часовой пояс UTC: Франция: (+2) летом (+1) зимой

**general - PILOT_NAME**

Имя Пилота

**general - GLIDER_NAMEx**

x от 1 до 4: позволяет ввести 4 названия крыла

**general - GLIDER_SELECT**

Позволяет выбрать 1 крыло из 4 возможных

**vario - SINKING_THRESHOLD**

default: -2.0<br>
Срабатывание порога снижения

**vario - CLIMBING_THRESHOLD**

default: 0.2<br>
порог срабатывания на подъем

**vario - NEAR_CLIMBING_SENSITIVITY**

default: 0.5<br>
Нулевая зона

от -10 до -2.0 низкий грубый звук<br>
от -2.0 до 0.2 без звука<br>
от 0.2 до 0.5 нулевой сигнал<br>
0.5 до 10 восходящие сигналы

**vario - ENABLE_NEAR_CLIMBING_ALARM**

default: 0<br>
1 = Сигнал о приближении к термику: сигнализирует, что вы входите или покидаете зону ближнего термика

**vario - ENABLE_NEAR_CLIMBING_BEEP**

default: 0<br>
1 = Функция «тепловой анализатор»: подавать звуковой сигнал, когда вы находитесь в зоне между VARIOMETER_CLIMBING_THRESHOLD и VARIOMETER_NEAR_CLIMBING_SENSITIVITY

**vario - DISPLAY_INTEGRATED_CLIMB_RATE**

default: 0<br>
1 = Отображение средней скорости снижения за период<br>
0 = Отображение мгновенной скорости снижения

**vario - CLIMB_PERIOD_COUNT**

default: 10<br>
время интегрирования для расчета скорости снижения

**vario - SETTINGS_GLIDE_RATIO_PERIOD_COUNT**

default: 20<br>
частота отображения скорости снижения

**vario - RATIO_CLIMB_RATE**

default: 2<br>
1 = Отображение коэффициента планирования<br>
2 = Отображение средней скорости снижения<br>
3 = Отображение обеих данных поочередно

**vario - RATIO_MAX_VALUE**

default: 30.0<br>
максимальное значение, используемое при расчете скорости снижения

**vario - RATIO_MIN_SPEED**

default: 10.0<br>
минимальное значение скорости, используемое при расчете скорости снижения

**vario - SENT_LXNAV_SENTENCE**

default: 1<br>
Bluetooth формат передачи<br>
1 = LXNAV<br>
0 = LK8000

**flightstart - FLIGHT_START_MIN_TIMESTAMP**

default: 15000 milliseconds<br>
Минимальное время между включением прибора и началом полета, в миллисекундах

**flightstart - FLIGHT_START_VARIO_LOW_THRESHOLD**

default: 0.5<br>
Минимальная вертикальная скорость в м/с (порог спуска / подъема) для начала записи

**flightstart - FLIGHT_START_VARIO_HIGH_THRESHOLD**

default: 0.5<br>
Максимальная вертикальная скорость в м/с (порог спуска / подъема) для начала записи

**flightstart - FLIGHT_START_MIN_SPEED**

default: 8 km/h<br>
Минимальная скорость относительно земли в км/ч для начала записи полета

**flightstart - VARIOMETER_RECORD_WHEN_FLIGHT_START**

default: 1<br>
0 = деактивирован, запись начнется, как только будет зафиксирован GPS<br>
1 = активировано, запись начнется при обнаружении начала полета (горизонтальная скорость больше FLIGHT_START_MIN_SPEED и вертикальная скорость больше FLIGHT_START_VARIO_LOW_THRESHOLD или меньше FLIGHT_START_VARIO_HIGH_THRESHOLD

### wifi.cfg #

Этот файл содержит параметры подключения Wi-Fi.<br>
Вы можете настроить до 4 сетей Wi-Fi

**SSID_1**

default: your_SSID1<br>
SSID of the first Wifi network

**PASSWORD_1**

default: your_PASSWORD_for SSID1<br>
Password of the first Wifi network

**SSID_2**<br>
**PASSWORD_2**


**SSID_3**<br>
**PASSWORD_3**


**SSID_4**<br>
**PASSWORD_4**

### variocal.cfg #

Этот файл содержит значения калибровки GNUVario.

**VERTACCEL_GYRO_CAL_BIAS_00**

default: 0x00

**VERTACCEL_GYRO_CAL_BIAS_01**

default: 0x00

**VERTACCEL_GYRO_CAL_BIAS_02**

default: 0x00

**VERTACCEL_GYRO_CAL_BIAS_03**

default: 0x00

**VERTACCEL_GYRO_CAL_BIAS_04**

default: 0x00

**VERTACCEL_GYRO_CAL_BIAS_05**

default: 0x00

**VERTACCEL_GYRO_CAL_BIAS_06**

default: 0x00

**VERTACCEL_GYRO_CAL_BIAS_07**

default: 0x00

**VERTACCEL_GYRO_CAL_BIAS_08**

default: 0x00

**VERTACCEL_GYRO_CAL_BIAS_09**

default: 0x00

**VERTACCEL_GYRO_CAL_BIAS_10**

default: 0x00

**VERTACCEL_GYRO_CAL_BIAS_11**

default: 0x00

**VERTACCEL_ACCEL_CAL_BIAS_00**

default: 0x00

**VERTACCEL_ACCEL_CAL_BIAS_01**

default: 0x00

**VERTACCEL_ACCEL_CAL_BIAS_02**

default: 0x00

**VERTACCEL_ACCEL_CAL_SCALE**

default: 0

**VERTACCEL_MAG_CAL_BIAS_00**

default: 0

**VERTACCEL_MAG_CAL_BIAS_01**

default: 0

**VERTACCEL_MAG_CAL_BIAS_02**

default: 0

**VERTACCEL_MAG_CAL_PROJ_SCALE**

default: 15535

**VERTACCEL_ACCEL_CAL_BIAS_MULTIPLIER**

default: 5

**VERTACCEL_MAG_CAL_BIAS_MULTIPLIER**

default: 5



### log.cfg #

Этот файл содержит значения конфигурации отладки.

**LOG_ENABLE**

default: 1<br>
Debugger активация
     
**LOG_SERIAL_ENABLE**

default: 1<br>
Активация сообщений в последовательный порт
     
**LOG_SD_ENABLE**

default: 1<br>
Активация сообщений на SD карту
      
**LOG_DEBUG_ENABLE**

default: 1<br>
Активация сообщений в режиме отладки ESP32

**MAIN_DEBUG**

default: 0<br>
Активация основных программных сообщений

**SCREEN_DEBUG**

default: 0<br>
Активация сообщений об управлении экраном

**GPS_DEBUG**

Default: 0<br>
Активация сообщений GPS

**BUTTON_DEBUG**

Default = 0<br>
Активация сообщений относительно управления кнопками

**MS5611_DEBUG**

Default: 0<br>
Активация сообщений о барометрическом датчике

**MPU_DEBUG**

Default: 0<br>
Активация сообщений об акселерометрах, гироскопе, ...
 
**SDCARD_DEBUG**

Default: 0<br>
Активация сообщений о SD-карте

**BT_DEBUG**

Default: 0<br>
Активация сообщений Bluetooth

**WIFI_DEBUG**

Default: 0<br>
Активация сообщений о WiFi

**SOUND_DEBUG**

Default: 0<br>
Активация звуковых сообщений

**DEEPSLEEP_DEBUG**

Default: 1<br>
Активация сообщений о режиме ожидания



