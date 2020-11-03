---
step: 7
description: Отладка
---

В этой главе будут описаны способы отладки, используемые в коде Gnuvario-E.

Со временем система отображения отладочной информации развивалась.

Сегодня в коде Gnuvario-E реализовано 3 способа.

**Способ 1**

Используя файл DebugConfig.h и println
      
#define ENABLE_DEBUG
     
#define PROG_DEBUG // debug principal program
      
ENABLE_DEBUG allows to activate debugging.
     
Затем для каждого типа отслеживаемой информации мы определяем или не определяем их.
Сообщения отображаются в мониторе последовательного порта путем добавления строк в код.

#ifdef SCREEN_DEBUG
    SerialPort.print ("Created task: Executing on core");
    SerialPort.println (xPortGetCoreID ());
#endif // SCREEN_DEBUG


**Способ 2**

В способе 2 также используется файл DebugConfig.h, но на выходе добавляется имя
исходного файла, имена переменных и строка.
     
В начале каждого исходного файла вы должны объявить об использовании функций отладки.

#include <DebugConfig.h>
       
#ifdef NMEAPARSER_DEBUG
#define ARDUINOTRACE_ENABLE 1
#else
#define ARDUINOTRACE_ENABLE 0
#endif
     
#define ARDUINOTRACE_SERIAL SerialPort
#include <ArduinoTrace.h>

Затем можно будет использовать функции:

TRACE();
Отображает номер строки, имя файла на мониторе последовательного порта.
      
DUMP (someValue);
На мониторе последовательного порта отобразит переменную, а так же файл и строку.
      
SDUMP (someText);
Отображает текс, номер строки, имя файла на мониторе последовательного порта.
       
**Способ 3**
             
Способ 3 записывает отладочную информацию в файл variolog.log.
Файл debug.cfg, описанный в разделе «конфигурация», используется для выбора сообщений для отображения.
          
Вам нужно будет использовать библиотеку variolog.h.

Возможные функции:

TRACELOG (type, module)
Сохраняет файл и строку в файле журнала.

DUMPLOG (type, module, variable)
Сохраняет переменную, файл и строку в файле журнала.

MESSLOG (type, module, Text)
Записывает сообщение с файлом и строкой в файле журнала.

INFOLOG (Text)
Сохраненяет текст в файле журнала.
                                                                                                    

