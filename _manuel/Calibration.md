---
step: 6
title: Руководство
description: Калибровка
---

**Важно откалибровать акселерометры**

GnuVario-E имеет акселерометр, который необходимо откалибровать.

Сначала в Windows или Mac установите [Python version 2 или version 3](https://www.python.org/). В Windows обязательно отметьте опцию **add to PATH variable**.

Install python 'numpy' library:
{% highlight shell_session %}
c:>pip install numpy 
{% endhighlight %}
       
Получите код {% include lienfichier.md name = "calibration.zip" lien = "file/calibration.zip"%}, который вы поместите в папку с именем, например, "калибровка"
      
Скопируйте {% include lienfichier.md name = "variocal.cfg" lien = "file/variocal.cfg"%} файл на SD карту
       
Убедитесь, что ваша SD-карта находится внутри вариометра.
         
Включите Gnuvario-E
Войдите в режим калибровки, нажав правую кнопку при запуске (на экране инициализации).
У вас есть несколько секунд, чтобы поставить вариометр на ровную поверхность и нажать центральную кнопку.

**Дождитесь 3 звуковых сигналов** затем начните вращать вариометр во всех плоскостях.
Вы должны сделать примерно 5-6 измерений на каждую плоскость вращения, ожидая звукового сигнала между каждым измерением.
Чем больше измерений вы сделаете, тем точнее будет калибровка.

**ВНИМАНИЕ, важно не забыть ни одной плоскости**

В конце нажмите левую кнопку вариометра, чтобы завершить калибровку. Варио перезапустится.

<iframe width = "560" height = "315" src = "https://www.youtube.com/embed/6yxoZcxxzVY" frameborder = "0" allow = "autoplay; encrypted-media" allowfullscreen> </iframe>

Это создаст «RECORD**.CAL» на SD-карте. Скопируйте этот файл в папку «best-fit-calibration» и при необходимости переименуйте его в «RECORD00.IGC».

В Windows или Mac, запустите **Idle** Python и запустите программу "calibrage/calibrer.py". Нажмите "F5" для запуска.
    
{%include manuelimg.md name="python_file.jpg"%}

или
      
{% highlight shell_session%}
c:> cd calibration
c: \ calibration> python calibrate.py
{% endhighlight%}

в Linux, просто запустите:

{% highlight shell_session%}
~ $ cd Arduino / best-fit-calibration
~ / best-fit-calibration $ python2 calibrate.py
{% endhighlight%}
      
Для завершения калибровки скопируйте все параметры калибровки в файл **/variocal.cfg** на SD-карте.

{%include manuelimg.md name="Calibrate_python.jpg"%}

{% highlight shell_session%}
Variocal.cfg file

[VERSION=1.0]

/* Calibration */
[VERTACCEL_GYRO_CAL_BIAS_00=0xff]
[VERTACCEL_GYRO_CAL_BIAS_01=0xff]
[VERTACCEL_GYRO_CAL_BIAS_02=0x3f]
[VERTACCEL_GYRO_CAL_BIAS_03=0xb3]
[VERTACCEL_GYRO_CAL_BIAS_04=0x00]
[VERTACCEL_GYRO_CAL_BIAS_05=0x00]
[VERTACCEL_GYRO_CAL_BIAS_06=0x00]
[VERTACCEL_GYRO_CAL_BIAS_07=0x00]
[VERTACCEL_GYRO_CAL_BIAS_08=0x01]
[VERTACCEL_GYRO_CAL_BIAS_09=0x00]
[VERTACCEL_GYRO_CAL_BIAS_10=0xf7]
[VERTACCEL_GYRO_CAL_BIAS_11=0xff]
[VERTACCEL_ACCEL_CAL_BIAS_00=4240]
[VERTACCEL_ACCEL_CAL_BIAS_01=12585]
[VERTACCEL_ACCEL_CAL_BIAS_02=17394]
[VERTACCEL_ACCEL_CAL_SCALE= -136]
[VERTACCEL_MAG_CAL_BIAS_00=11068]
[VERTACCEL_MAG_CAL_BIAS_01=20912]
[VERTACCEL_MAG_CAL_BIAS_02=17504]
[VERTACCEL_MAG_CAL_PROJ_SCALE=-17821]
[VERTACCEL_ACCEL_CAL_BIAS_MULTIPLIER=7]
[VERTACCEL_MAG_CAL_BIAS_MULTIPLIER=7]

{% endhighlight %}
