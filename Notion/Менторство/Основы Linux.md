---
Категория:
  - DS-материал
---
[Подборка ресурсов по Линукс](https://proglib.io/p/linux-courses) - ==разобрать==

  

## Книги

- [The Linux Command Line](https://cloud.mail.ru/public/84iq/4WXUWaKe2) ❗️- потрясающая книга (для начала достаточно прочитать главы 1-6, 9, 11, 14, 18)

## Курсы

- [Введение в Linux на Stepik](https://stepik.org/course/73) — знакомство с базовыми возможностями
- [rototo.cloud - курсы по технологиям DevOps](https://rotoro.cloud/landing.html) (платно)

## Полезное

- [Как создавать свои команды в Python](https://click.palletsprojects.com/en/8.1.x/)

## Работа с окружениями

1. **python3 -m pip install virtualenv**
2. **virtualenv env_name**
3. **cd ./папка_проекта_где_лежит_env_name**
4. **source env_name/bin/activate**
5. **pip install pandas**
6. **pip show pandas**
7. **deactivate**

  

  

  

- **python3 -m pip install --user virtualenv** -- установили virtualenv
- **virtualenv env_pymc** -- создали окружение env_pymc (папка)
- **cd ./папка_проекта_где_лежит_env_pymc** -- находимся в папке проекта
- **source env_pymc/bin/activate** -- активируем окружение env_pymc
- **pip install jupyter notebook** -- устанавливаем юпитер ноутбук
- **jupyter notebook** -- заходим в ноутбук в окружении env_pymc
- **pip show numpy** -- проверяем, что env_pymc пустое