---
step: 7
title: Руководство
description: Калибровка
---

**Важно откалибровать акселерометры**

GnuVario-E имеет акселерометр, который необходимо откалибровать.

## Процедура калибровки

Калибровка выполняется в несколько этапов::
1. [Очистка SD-карты](#очистка-SD-карты)
2. [Измерение экспериментальных точек](#измерения)
3. Расчет калибровочных значений
4. Сохранение значений калибровки на SD-карту

Начиная с версии 0.10.2 WEB-сервера, шаги 3 и 4 упрощены.

### Очистка SD карты

**1.** Сброс файла `variocal.cfg`

{% include manuelimg.md name="calibrationweb1EN.jpg" %}

На WEB-сервере, на вкладке «SD-карта» или непосредственно на SD-карте убедитесь, что файл `variocal.cfg` действительно является пустым файлом, доступным в папке `RootSD`, и содержит:

{% highlight shell_session %}
Пустой файл `variocal.cfg`:

[VERSION=1.0]

/* Calibration */
[VERTACCEL_GYRO_CAL_BIAS_00=0x00]
[VERTACCEL_GYRO_CAL_BIAS_01=0x00]
[VERTACCEL_GYRO_CAL_BIAS_02=0x00]
[VERTACCEL_GYRO_CAL_BIAS_03=0x00]
[VERTACCEL_GYRO_CAL_BIAS_04=0x00]
[VERTACCEL_GYRO_CAL_BIAS_05=0x00]
[VERTACCEL_GYRO_CAL_BIAS_06=0x00]
[VERTACCEL_GYRO_CAL_BIAS_07=0x00]
[VERTACCEL_GYRO_CAL_BIAS_08=0x00]
[VERTACCEL_GYRO_CAL_BIAS_09=0x00]
[VERTACCEL_GYRO_CAL_BIAS_10=0x00]
[VERTACCEL_GYRO_CAL_BIAS_11=0x00]
[VERTACCEL_ACCEL_CAL_BIAS_00=0]
[VERTACCEL_ACCEL_CAL_BIAS_01=0]
[VERTACCEL_ACCEL_CAL_BIAS_02=0]
[VERTACCEL_ACCEL_CAL_SCALE=0]
[VERTACCEL_MAG_CAL_BIAS_00=0]
[VERTACCEL_MAG_CAL_BIAS_01=0]
[VERTACCEL_MAG_CAL_BIAS_02=0]
[VERTACCEL_MAG_CAL_PROJ_SCALE=-16689]
[VERTACCEL_ACCEL_CAL_BIAS_MULTIPLIER=6]
[VERTACCEL_MAG_CAL_BIAS_MULTIPLIER=4]

{% endhighlight %}

**2.** Удалите файл `RECORD00.CAL` если он есть.

### Измерения

Убедитесь, что ваша SD-карта находится внутри вариометра.
         
Включите Gnuvario-E или перезагрузите его. 
Войдите в режим калибровки, нажав правую кнопку при запуске (на экране инициализации).
У вас есть несколько секунд, чтобы поставить вариометр на ровную поверхность и нажать центральную кнопку.

Для достижения оптимального результата калибровку не следует выполнять по оси север / юг. Если вы знаете, где находится север, попробуйте сместить вариометр на 45° от севера (когда он ровно лежит на столе).

**Дождитесь 3 звуковых сигналов** затем начните вращать вариометр во всех плоскостях, используя подставку (картон, книгу), чтобы стабилизировать его на краю. 
Вы должны сделать примерно 5-6 измерений на каждую плоскость вращения, ожидая звукового сигнала между каждым измерением.
Чем больше измерений вы сделаете, тем точнее будет калибровка.

**ВНИМАНИЕ, важно не забыть ни одной плоскости**

В конце нажмите левую кнопку вариометра, как минимум на две секунды, чтобы завершить калибровку. Варио перезапустится.

<iframe width = "560" height = "315" src = "https://www.youtube.com/embed/6yxoZcxxzVY" frameborder = "0" allow = "autoplay; encrypted-media" allowfullscreen> </iframe>

### Расчет и сохранение калибровочных значений

Вернитесь в WEB-сервер, перейдите на вкладку «Настройки», затем «Калибровка».

{% include manuelimg.md name="calibrationweb3EN.jpg" %}

Нажмите «Начать создание файла калибровки». Файл `RECORD00.CAL` созданный на этапе калибровки, отправляется на удаленный сервер, который вычисляет правильные значения и обновляет файл `variocal.cfg`.

Если появляется сообщение «Расчет калибровочного файла ОК», значит, все прошло успешно. Ваш вариометр откалиброван.

{% include manuelimg.md name="calibrationweb2EN.jpg" %}

## Расчет значений калибровки с помощью скрипта Python

**Если [описанная выше](#расчет-и-сохранение-калибровочных-значений) полуавтоматическая процедура не работает**, вы можете рассчитать значения калибровки с помощью скрипта Python после [очистки SD-карты](#очистка-SD-карты) и [измерения экспериментальных точек](#измерения).

### Инструкции для пользователей Windows и Mac

**1.** Сначала установите в Windows или Mac [Python version 2 или version 3](https://www.python.org/downloads/). В Windows обязательно отметьте опцию **add to PATH variable**.

{% include manuelimg.md name="python6.jpg" %}

Install python 'numpy' library:
{% highlight shell_session %}
c:>pip install numpy 
{% endhighlight %}

Установка библиотеки на MacOS:
{% highlight shell_session %}
~ $ sudo pip3 install numpy 
{% endhighlight %}
       
**2.** Скопируйте папку «calibration», находящуюся в `RootSD`.

**3.**  В Windows или Mac, запустите **Idle** Python и запустите программу `get-pip.py` находящуюся в `calibration/Installation`. Нажмите `F5` для запуска.

{% include manuelimg.md name="python1.jpg" %}

**4.** Когда выполнение будет завершено, откройте командную строку Windows.

Скопируйте и выполните следующую команду: `python -m pip install --user numpy scipy matplotlib ipython jupyter pandas sympy nose`

{% include manuelimg.md name="python2.jpg" %}

После выполнения команды перезагрузите компьютер.

**5.** Удалите файл `RECORD00.CAL` уже находящийся в папке `calibration`

**6.** Скопируйте файл `RECORD00.CAL` созданный на SD-карте, в папку `calibration`

**7.** В Windows или Mac, запустите Idle Python и запустите программу `calibrate.py` который находится в папке `calibration`

{% include manuelimg.md name="python3.jpg" %}

**8.** Нажмите `F5` для запуска.

{% include manuelimg.md name="python4.jpg" %}

**9.** Вы также можете написать команду непосредственно `python calibrate.py` в командной строке Windows, после изменения каталога (команды `cd`) для перехода в папку `calibration` :

{% highlight shell_session%}
c:> cd calibration
c: \ calibration> python calibrate.py
{% endhighlight%}

в Linux, просто запустите:

{% highlight shell_session%}
~ $ cd calibration
~ / calibration $ python3 calibrate.py
{% endhighlight%}

{% include manuelimg.md name="python5.jpg" %}

**10.** По окончании выполнения программы скопируйте все параметры калибровки в файл `variocal.cfg` находящийся на SD-карте.

{% highlight shell_session %}
Пример обновленного файла `variocal.cfg` со значениями калибровки:

[VERSION=1.0]

/* Calibration */
[VERTACCEL_GYRO_CAL_BIAS_00=0xad]
[VERTACCEL_GYRO_CAL_BIAS_01=0x80]
[VERTACCEL_GYRO_CAL_BIAS_02=0x0f]
[VERTACCEL_GYRO_CAL_BIAS_03=0x80]
[VERTACCEL_GYRO_CAL_BIAS_04=0x00]
[VERTACCEL_GYRO_CAL_BIAS_05=0x1e]
[VERTACCEL_GYRO_CAL_BIAS_06=0xfd]
[VERTACCEL_GYRO_CAL_BIAS_07=0x3f]
[VERTACCEL_GYRO_CAL_BIAS_08=0x01]
[VERTACCEL_GYRO_CAL_BIAS_09=0x00]
[VERTACCEL_GYRO_CAL_BIAS_10=0xf4]
[VERTACCEL_GYRO_CAL_BIAS_11=0xff]
[VERTACCEL_ACCEL_CAL_BIAS_00=5101]
[VERTACCEL_ACCEL_CAL_BIAS_01=16835]
[VERTACCEL_ACCEL_CAL_BIAS_02=5334]
[VERTACCEL_ACCEL_CAL_SCALE= -433 ]
[VERTACCEL_MAG_CAL_BIAS_00=-10569]
[VERTACCEL_MAG_CAL_BIAS_01=-2289]
[VERTACCEL_MAG_CAL_BIAS_02=18776]
[VERTACCEL_MAG_CAL_PROJ_SCALE= -3553 ]
[VERTACCEL_ACCEL_CAL_BIAS_MULTIPLIER= 8 ]
[VERTACCEL_MAG_CAL_BIAS_MULTIPLIER= 6 ]
{% endhighlight %}


**11.** Установите SD-карту в вариометр. Теперь он откалиброван.

### Инструкции для пользователей Linux

1. Откройте консольный терминал

1. Создайте временный каталог, в котором будет выполняться калибровка (в приведенном ниже примере он называется `demo`, затем перейдите в этот новый каталог.

   ```bash
   mkdir demo
   cd demo
   ```

1. Скопируйте папку `calibration` из `RootSD` в папку `demo`, затем перейдите в этот новый каталог.

   Если у вас есть программное обеспечение `git`,  не очень хороший способ сделать это - клонировать [репозиторий программного обеспечения](https://github.com/prunkdump/GNUVario-TTGO-T5.git) из Github, а затем получить там папку:

   ```bash
   git clone https://github.com/prunkdump/GNUVario-TTGO-T5.git
   cp -r "./GNUVario-TTGO-T5/Sources/RootSd/Pour v0.8b6/RootSD/calibration" .
   cd calibration
   ```

1. Поскольку он не очень чистый, вы можете сделать небольшую уборку перед тем, как начать.

   ```bash
   rm -rf *.pyc *.old __pycache__
   ```

1. Скопируйте сделанные ранее [измерения](#измерения) — , то есть файл `RECORD00.CAL`, созданный на SD-карте, в папку `calibration`

1. Обновление `pip` и восстановление `pipenv` (что позволит вам делать все в виртуальной среде с правильной версией Python, а затем удалять ее, чтобы не загрязнять ваш компьютер)

   ```bash
   python -m pip install --upgrade pip
   python -m pip install pipenv
   ```

1. Создание и запуск виртуальной среды

   ```bash
   python -m pipenv --python 3.7
   python -m pipenv shell
   ```

1. Установка необходимых библиотек в окружение

   ```bash
   python -m pip install numpy scipy matplotlib ipython jupyter pandas sympy nose
   ```

1. Калибровка

   ```bash
   python calibrate.py
   ```

   Скопируйте сгенерированные значения в файл `variocal.cfg` (см. Выше пример файла `variocal.cfg` обновленного значениями калибровки)

1. Выйдите из виртуальной среды, затем удалите виртуальную среду и временную рабочую папку.

   ```bash
   exit
   pip -m pipenv --rm
   cd ..
   cd ..
   rm -rf demo
   ```
