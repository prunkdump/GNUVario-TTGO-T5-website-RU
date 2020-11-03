---
step: 3
description: Получение кода
---

Самый простой способ: скачать zip файл.
----------------------------------

Исходный код можно скачать напрямую как zip файл с [GitHub](https://github.com/prunkdump/GNUVario-TTGO-T5). Просто нажмите **Clone or download** и **Download zip**.

![GitHub download zip]({{"/assets/code_img/code1.jpg" | absolute_url}})

Распакуйте ZIP в любое место на ваш выбор. Там создастся папвка **Gnuvario-TTGO-T5-master**.

![GitHub zip download]({{"/assets/code_img/code2.jpg" | absolute_url}})

При установке Arduino IDE обычно создается папка **Arduino** в вашей папке документов.<BR>
Убедитесь, что эта папка пуста и скопируйте в нее Sources\Beta Code\Gnuvario-E и Sources\Beta Code\libraries из папки **Gnuvario-TTGO-T5-master**.

**ВАЖНО**: В этой папке должны быть только файлы библиотек и проекта Gnuvario-E.

![GitHub zip download]({{"/assets/code_img/dossierRootArduino.jpg" | absolute_url}})

Другой способ: использовать Git
-----------------------------

Вы так же можете получить исходный код используя [Git](https://git-scm.com/). Это лучший способ, потому что с Git вы можете обновить код, сохранив настройки. 

Так что установите Git и убедитесь, что папка **Arduino** в вашем домашнем каталоге пуста. С помощью bash перейдите в каталог **Arduino**, клонируйте репозиторий и создайте для себя ветку.

{% highlight shell_session%}
~ $ cd Arduino
~ / Arduino $ git clone https://github.com/prunkdump/GNUVario-TTGO-T5.git.
~ / Arduino $ git checkout -b myversion
{% endhighlight%}

Итак, всякий раз, когда вы хотите обновить код, введите следующие команды из каталога **Arduino**. Первые две строки сохраняют ваши изменения. Следующие две строки загружают изменения из основной ветки GitHub. Последний применяет изменения к вашей версии.

{% highlight shell_session%}
~ / Arduino $ git add -A
~ / Arduino $ git commit -m 'change'
~ / Arduino $ git checkout master
~ / Arduino $ git pull
~ / Arduino $ git checkout myversion
~ / Arduino $ git merge master
{% endhighlight%}