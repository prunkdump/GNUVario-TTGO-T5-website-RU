---
step: 2
description: IDE VSCode - PlatformIO
---

PlatformIO также можно использовать для компиляции кода и загрузки его.
Мы будем использовать PlarformIO с Visual Studio IDE (VSCode).

Эта IDE доступна для Windows, Linux и Mac; далее мы опишем процедуру установки под Windows.

Полная документация по установке PlatformIO с VSCode [описана здесь](https://docs.platformio.org/en/latest/ide/vscode.html); вот резюме.

### Установка VSCode

Установочный файл доступен по ссылке [https://code.visualstudio.com/](https://code.visualstudio.com/).
В среде Windows мы загрузим файл **VSCodeUserSetup-x64-1.42.1.exe**.
Дважды щелкните этот файл, и мастер установки запустится; оставьте параметры по умолчанию.

### Установка PlatformIO

PlatformIO будет работать в среде VSCode IDE. Чтобы установить его, вы должны запустить VSCode (ярлык называется «Visual Studio Code»), затем нажать значок расширений на вертикальной панели слева (или нажать Ctrl + Shift + X).

{% include codeimg.md name = "platformio-01.jpg"%}

В области ввода введите «platformio». Будет предложено несколько расширений; нажмите кнопку «установить» расширения «PlatformIO IDE».

После установки значок PlatformIO появится на вертикальной панели слева, а значок «PlatformIO: Home» появится на горизонтальной панели значков внизу:

{% include codeimg.md name = "platformio_icones.jpg"%}

Установка VSCode - Platformio IDE завершена.
