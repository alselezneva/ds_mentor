---
Категория:
  - DS-материал
---
## Документация

- [Официальная документация](https://docs.python.org/3/tutorial)
- [PEP8](https://pep8.org/)
- [The Elements of Python Style](https://github.com/amontalenti/elements-of-python-style) – руководство по стилю кода

  

## Roadmap

- [Интерактивная roadmap](https://roadmap.sh/python)

![[_Изображения/image 2.png|image 2.png]]

  

![[_Изображения/image 1 2.png|image 1 2.png]]

## Первые шаги

1. Установить Python, для этого нужно скачать его с сайта [python.org](https://www.python.org/downloads/).
2. Установить [IDE](https://ru.wikipedia.org/wiki/%D0%98%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D0%B0%D1%8F_%D1%81%D1%80%D0%B5%D0%B4%D0%B0_%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8) для работы (какая больше понравится). 
    1. [PyCharm](https://ru.wikipedia.org/wiki/PyCharm). Скачать можно с сайта [JetBrains](https://www.jetbrains.com/pycharm/). Можно установить `Community`.
    2. [VS Code](https://ru.wikipedia.org/wiki/Visual_Studio_Code). Скачать можно с официального сайта: [code.visualstudio.com](https://code.visualstudio.com/).
    3. [Anaconda](https://www.anaconda.com/what-is-anaconda/). Скачать можно с официального сайта: [anaconda.com](https://www.anaconda.com/download/).
3. Установить и настроить [Flake8](https://flake8.pycqa.org/en/latest/)

## Основы Python

### **Темы**

- Ввод / вывод (print, input)
- Типы данных и структуры (целые числа, дробные числа, строки, bool, списки, кортежи, словари, множества) + что значит изменяемость
- Переменные и выражения
- Условные операторы (if / elif / else)
- Циклы (for / while)
- Функции + область видимости
- Зачем нужен `__name__ == "__main__"`

### Ресурсы

- [Хендбук по Python от Яндекса](https://education.yandex.ru/handbook/python)
- [Программирование на Python](https://stepik.org/course/67)
- [Python: основы и применение](https://stepik.org/course/512)
- [Инди-курс программирования на Python](https://stepik.org/course/63085)
- [Поколение Python: курс для начинающих](https://stepik.org/course/58852/info)
- [Поколение Python: курс для продвинутых](https://stepik.org/course/68343/info)
- [Добрый, добрый Python с Сергеем Балакиревым](https://stepik.org/course/100707)
- [Самоучитель Python](https://pythonworld.ru/samouchitel-python)
- [Питонтьютер](http://pythontutor.ru)

## Объектно-ориентированное программирование

### Темы

- Классы и объекты
- Переменные (атрибуты) класса и объекта
- Магические методы, статические методы, методы класса
- Перегрузка операторов
- Наследование (виды наследования, mro, super)
- Полиморфизм
- Инкапсуляция (публичные, защищенные, приватные методы / атрибуты)
- Абстракция

### Ресурсы

- [ООП на Python: концепции, принципы и примеры реализации](https://proglib.io/p/python-oop) - статья
- [ООП: Объектно-ориентированное программирование на Python](https://stepik.org/course/114354) ❗️(платно)
- [Добрый, добрый Python ООП](https://stepik.org/course/116336) ❗️ (платно)
- [Самоучитель Python](https://pythonworld.ru/samouchitel-python)
- [Курс на Youtube про ООП](https://youtube.com/playlist?list=PLNi5HdK6QEmX9fxp3_IBFx1O5tiTmKlYm)

## Обработка исключений

### **Темы**

- Обзор исключений в питоне
- Конструкция try - except - else - finally
- raise
- Как создавать свои собственные исключения

### **Ресурсы**

- [ООП: Объектно-ориентированное программирование на Python](https://stepik.org/course/114354) ❗️(платно)
- ["Поколение Python": курс для профессионалов](https://stepik.org/course/82541)❗️(платно)

## Функциональное программирование

### Темы

- Распаковка и запаковка аргументов
- Лямбда-выражения
- List / Set / Dict Comprehension
- Рекурсия
- Чистые функции
- Функции высшего порядка (map, filter, reduce) + zip
- Замыкание
- Итератор, генератор, декоратор

### Ресурсы

- [Функциональное программирование на Python](https://stepik.org/course/195619) ❗️
- [Документация: функциональное программирование](https://docs.python.org/3/howto/functional.html)
- [Самоучитель Python](https://pythonworld.ru/samouchitel-python)
- [Про функциональное программирования на канале Тимофея Хирьянова](https://www.youtube.com/watch?v=3Dmi4b8MkMM) - лекция
- [Про Map, filter, reduce, zip](https://youtu.be/UDthAJmD3EQ)- лекция
- [Про замыкание](https://stepik.org/lesson/372078/step/8?unit=359632) (step в курсе Инди-курс программирования на Python)
- [Про замыкание 2](http://uneex.ru/LecturesCMC/PythonIntro2022/04_FunctionsClosure)

## Модули и библиотеки

### Темы

- Импортирование модулей (в т.ч. из директории выше)
- Создание модулей (зачем нужен `__init__.py`)
- Работа с окружениями (**venv**) и менеджерами пакетов (**pip**)
- Использование **os** и **pathlib**
- Написание документации (**docstrings**)

### Ресурсы (не покрывают все темы)

- [[rabotasmodulyamisozdaniepodkl]] - статья на pythonworld.ru
- [Документация: Modules](https://docs.python.org/3/tutorial/modules.html)
- [Интересные библиотеки python](https://habr.com/ru/company/edison/blog/474622/) - список интересных библиотек

## Работа с файлами

### Темы

- Форматирование строк
- Открытие, чтение, запись и закрытие файлов
- Режимы работы с файлами
- Контекстный менеджер `with`
- Курсор
- Работа с CSV / JSON / PICKLE файлами

### Ресурсы

- [Про работу с файлами](https://youtu.be/oRr_bEXJbV0)
- [CSV](https://youtu.be/Pp2sMniG0FU)

## Разработка графических интерфейсов (?)

### Темы

- Tkinter
- PyQt
- PyGTK
- wxPython

### Ресурсы

- [Документация: Tkinter](https://docs.python.org/3/library/tkinter.html)
- [Плейлист разработок GUI на PyQt (1)](https://www.youtube.com/playlist?list=PL6plRXMq5RADiWZuyZvVYnhncVixVKgBN)
- [Плейлист разработок GUI на PyQt (2)](https://youtube.com/playlist?list=PLKl9v2TQvIkq4i_hZwZ1PmobxJSkIGwBf)

## Регулярные выражения (?)

### Темы

- Поиск шаблонов
- Метасимволы
- Квантификаторы
- Группы
- Подстановка

### Ресурсы

- [Плейлист про регулярные выражения на Youtube](https://youtube.com/playlist?list=PLmSBSL0-aSgkT_l0K0pXdfIKEPJyOZl7c)
- [https://www.regexpal.com/](https://www.regexpal.com/)
- [https://habr.com/ru/articles/349860/](https://habr.com/ru/articles/349860/)
- [https://tproger.ru/translations/regular-expression-python](https://tproger.ru/translations/regular-expression-python)
- [https://proglib.io/p/regexp-digest](https://proglib.io/p/regexp-digest)

## Параллельное и асинхронное выполнение

### Темы

- Контекстный менеджер
- Многопоточность (threading)
- Многопроцессность (multiprocessing)
- Асинхронное программирование (asyncio)

### Ресурсы

- [Многопоточный Python](https://stepik.org/course/190100) ❗️(платно)
- [Асинхронный Python](https://stepik.org/course/170777) ❗️(платно)

## Работа с базами данных (?)

### Темы

- 1

### Ресурсы

- 1

## Веб-разработка (?)

### Темы

- HTML / CSS
- Запросы HTTP
- Flask / Django
- REST API

### Ресурсы

- [Getting started with Django](https://www.djangoproject.com/start/)
- [Django](https://youtube.com/playlist?list=PLA0M1Bcd0w8xO_39zZll2u1lz_Q-Mwn1F)
- [Введение во Flask](https://www.youtube.com/playlist?list=PLXmMXHVSvS-AjwTOtiW1DXFYTgUlrUmHV)
- [HTML & CSS](https://youtube.com/playlist?list=PLMB6wLyKp7lV9YoWTMCztq-KXYhYPB09K)
- [REST API](https://youtu.be/v7zq1DntN_Y)

## Веб-скрапинг

### Темы

- Использование библиотек BeautifulSoup, Scrapy.
- Работа с HTML и CSS селекторами для извлечения данных.

### Ресурсы

- [WEB Парсинг на Python](https://stepik.org/course/104774) ❗️(платно)
- [https://pythonist.ru/vebskrejping-novostnyh-statej-v-5-strochek-koda-na-python/](https://pythonist.ru/vebskrejping-novostnyh-statej-v-5-strochek-koda-na-python/)

## Интерпретатор (?)

### Темы

- Использование интерпретатора для быстрого выполнения и отладки кода.
- Запуск скриптов и работа с командной строкой.
- **Bytecode ?**
- **Виртуальная машина ?**

### Ресурсы

- **Bytecode:** В открытом доступе материалов мало но будет полезно почитать [habr](https://habr.com/ru/articles/206420/) и прочитать [документацию](https://docs.python.org/3/library/dis.html). (вообще уметь читать документацию очень важно)
- почитайте статьи [часть1](https://habr.com/ru/articles/501338/) и [часть2](https://habr.com/ru/articles/501920/)
- И возьмем [git](https://github.com/ElephantT/Virtual-machine-for-Python-3.8-Interpreter) из школы анализа данных в котором уже написаны тесты, виртуальная машина и все что нужно для запуска, но эта виртуальная машина написана для более старых версий питона, и ваша задача переписать на новую версию питона

## Паттерны проектирования

### Темы

- Основные паттернов проектирования: Singleton, Factory, Observer.

### Ресурсы

- [Книга “Паттерны проектирования”](https://cloud.mail.ru/public/fpMS/e6tWwiHNS)
- [Книга “Шаблоны корпоративных приложений”](https://cloud.mail.ru/public/i36M/dFRsD7rgY)
- [Книга “Паттерны объектно-ориентированного проектировния”](https://cloud.mail.ru/public/hQta/hrRRGz9bk)

  

## Практика

1. [HackerRank](https://www.hackerrank.com/)
2. [LeetCode](https://leetcode.com/)
3. [Codewars](https://www.codewars.com/)

## Вопросы для подготовки к интервью

- [Вопросы для подготовки к Python Developer интервью](https://github.com/danilakritsky/python-interview-questions?tab=readme-ov-file)
- [Разбор вопросов для собеседования](https://www.notion.so/https-github-com-alselezneva-dashboard_games-36e8db7f9ee64d78a5527ed8b6b3c91f?pvs=21)
- [Полный список вопросов с собеседований по Python для дата-сайентистов и инженеров](https://cloud.vk.com/blog/spisok-voprosov-s-sobesedovaniy-python-dlya-data-sayentistov)

## Полезные ресурсы

- [Книга “Python - к вершинам мастерства”](https://cloud.mail.ru/public/69wQ/UVoHJjGJ6)
- [Книга “Изучаем Python” [Том 1, 5-е издание] [2019] Марк Лутц](https://cloud.mail.ru/public/hg4C/n5AY4MJ2C)
- [Книга “Изучаем Python” [Том 2, 5-е издание] [2020] Марк Лутц](https://cloud.mail.ru/public/3VNq/yaM3G2Kv7)
- [20 лучших бесплатных книг по Python для начинающих и продвинутых программистов](https://uproger.com/20-luchshih-besplatnyh-knig-po-python-dlya-nachinayushhih-i-prodvinutyh-programmistov/)