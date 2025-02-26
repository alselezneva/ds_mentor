---
Категория:
  - MOCK-интервью
---
добавить оптимизация в sql в мок

++ добавить про оптимизацию и каскадное удаление

EXPLAIN  
SELECT ...  

select *  
from system.tables  

system.processes

select *  
from system.query_log  

  

**Задачи для Data Engineer (SQL/Python)**

# **Цель интервью**

Целью интервью является оценка технических навыков и компетенций кандидата на позицию Data Engineer. Мы стремимся определить уровень владения SQL и базами данных, а также знание Python для выполнения задач, связанных с обработкой, анализом и управлением данными. Интервью включает проверку теоретических знаний, практических навыков и умение решать реальные задачи, с которыми кандидат может столкнуться на данной позиции. В ходе интервью будут рассмотрены следующие аспекты:

1. **Понимание и умение работать с реляционными базами данных и SQL.** Это включает знание основных команд SQL, концепций нормализации и денормализации данных, работы с индексами, транзакциями, а также умение выполнять сложные запросы и соединения данных.
2. **Знание принципов работы с большими данными (Big Data) и системами OLTP и OLAP.** Важно понимать разницу между системами онлайн-обработки транзакций и аналитическими системами, а также уметь применять подходящие решения для различных задач.
3. **Навыки программирования на Python.** Проверка знания основных концепций языка, работы с данными, написания функций, использования библиотек и инструментов, часто применяемых в работе Data Engineer.
4. **Решение практических задач.** Кандидат должен продемонстрировать способность решать практические задачи, которые могут возникнуть в повседневной работе, используя как SQL, так и Python.

## **Секция 1: SQL и базы данных**

Цель задать 3-4 вопроса для оценки уровня владение **SQL** и в случае успешных ответов перейти на задачи **SQL**.

### **Вопросы:**

1. **Что такое индекс в базе данных и какие типы индексов существуют?**
    - Индекс – это структура данных, которая улучшает скорость выполнения запросов в базе данных. Типы индексов включают: уникальные индексы, первичные ключи, кластерные и некластерные индексы, полнотекстовые индексы.
2. **Чем отличается OLTP от OLAP?**
    - OLTP (Online Transaction Processing) системы ориентированы на управление транзакциями, частыми и малыми по объему операциями. OLAP (Online Analytical Processing) системы предназначены для аналитики и обработки больших объемов данных для анализа и отчетности.
3. **Что такое нормализация и денормализация?**
    - Нормализация – процесс структурирования базы данных для минимизации избыточности и обеспечения целостности данных, 1,2,3 нормальная форма. Денормализация – процесс добавления избыточности для увеличения производительности запросов, star схема или другие.
4. **Что такое транзакция и какие свойства транзакций существуют?**
    - Транзакция – это последовательность операций, которая выполняется как единое целое. Свойства транзакций: ACID (Atomicity, Consistency, Isolation, Durability).
5. **Как реализовать связь "многие ко многим" в реляционной базе данных?**
    - Для реализации связи "многие ко многим" необходимо создать промежуточную таблицу, которая содержит внешние ключи к двум связанным таблицам.
6. **Что такое внешние ключи и зачем они нужны?**
    - Внешний ключ – это поле или группа полей в таблице, которые указывают на первичный ключ в другой таблице. Они используются для обеспечения ссылочной целостности данных.
7. **Как работает команда JOIN и какие типы соединений существуют?**
    - Команда JOIN используется для объединения строк из двух или более таблиц на основе связанного столбца. Типы соединений включают INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL OUTER JOIN.
8. **Что такое подзапрос и какие типы подзапросов существуют?**
    - Подзапрос – это запрос, который находится внутри другого запроса. Типы подзапросов: подзапросы в SELECT, WHERE, FROM, EXISTS, и скалярные подзапросы.
9. **Какие есть типы данных в SQL и как выбрать подходящий тип данных для поля?**
    - Типы данных в SQL включают: числовые (INT, FLOAT), строковые (VARCHAR, TEXT), даты и времени (DATE, TIMESTAMP), и другие. Выбор типа данных зависит от природы данных, которые будут храниться в поле.
10. **Что такое схема базы данных и зачем она нужна?**
    - Схема базы данных – это структура, которая определяет организацию данных в базе, включая таблицы, представления, индексы, процедуры и т.д. Она нужна для управления и упорядочивания данных.

### **Задача на SQL:**

Таблица `**customers**`:

```Java/C/C++/C#
CREATE TABLE customers (
id INT PRIMARY KEY,
name VARCHAR(100) );
```

Таблица `**orders**`:

```Java/C/C++/C#
CREATE TABLE orders (
id INT PRIMARY KEY,
customer_id INT,
order_date DATE,
amount DECIMAL(10, 2),
FOREIGN KEY (customer_id) REFERENCES customers(id)
);
```

**Вставьте несколько записей в таблицы:**

Таблица `**customers**`:

```Java/C/C++/C#
INSERT INTO customers (id, name) VALUES (1, 'Alice'), (2, 'Bob'), (3, 'Charlie');
```

Таблица `**orders**`:

```Java/C/C++/C#
INSERT INTO orders (id, customer_id, order_date, amount) VALUES
(1, 1, '2023-01-15', 100.00),
(2, 1, '2023-01-20', 150.00),
(3, 2, '2023-01-25', 200.00),
(4, 2, '2023-02-01', 250.00),
(5, 3, '2023-02-05', 300.00),
(6, 3, '2023-02-10', 350.00),
(7, 1, '2023-02-15', 400.00),
(8, 2, '2023-02-20', 450.00),
(9, 3, '2023-03-01', 500.00),
(10, 1, '2023-03-05', 550.00);
```

**Вопросы:**

1. Что будет возвращать запрос left join:

```Java/C/C++/C#
SELECT customers.id AS customer_id, customers.name, orders.id AS order_id, orders.amount

FROM customers

LEFT JOIN orders ON customers.id = orders.customer_id;
```

1. Что будет возвращать запрос inner join:

```Java/C/C++/C#
SELECT customers.id AS customer_id, customers.name, orders.id AS order_id, orders.amount
FROM customers
INNER JOIN orders ON customers.id = orders.customer_id;
```

1. Написать запрос, который возвращает сумму заказов за каждый месяц, можно использовать функцию агрегирования `SUM` и группировку по месяцу. Предположим, что у нас есть таблица `orders` с колонками `order_date` и `amount`

**Ответ:**

```Java/C/C++/C#
SELECT

    DATE_TRUNC('month', order_date) AS month,

    SUM(amount) AS total_amount

FROM

    orders

GROUP BY

    DATE_TRUNC('month', order_date)

ORDER BY

    month;
```

1. Напишите запрос, который:
2. Возвращает информацию о каждом заказе.
3. Использует оконные функции для вычисления следующих дополнительных столбцов:
    - Кумулятивная сумма заказов для каждого клиента, отсортированная по дате заказа.
    - Средняя сумма заказов для каждого клиента, отсортированная по дате заказа.
    - Номер строки для каждого заказа в рамках каждого клиента, отсортированная по дате заказа.

Ответ:

```Java/C/C++/C#
SELECT
    id,
    customer_id,
    order_date,
    amount,
    SUM(amount) OVER (PARTITION BY customer_id ORDER BY order_date) AS cumulative_sum,
    AVG(amount) OVER (PARTITION BY customer_id ORDER BY order_date) AS average_amount,
    ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY order_date) AS row_number
FROM
    orders
ORDER BY
    customer_id,
    order_date;
```

**Пояснения:**

- `SUM(amount) OVER (PARTITION BY customer_id ORDER BY order_date)`: вычисляет кумулятивную сумму заказов для каждого клиента, отсортированных по дате заказа.
- `AVG(amount) OVER (PARTITION BY customer_id ORDER BY order_date)`: вычисляет среднюю сумму заказов для каждого клиента, отсортированных по дате заказа.
- `ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY order_date)`: вычисляет номер строки для каждого заказа в рамках каждого клиента, отсортированных по дате заказа.

## **Секция 2: Python и Spark**

Цель задать 3-4 вопроса для оценки уровня владение **Python** и в случае успешных ответов перейти на задачи **Python**.

**Вопросы Python:**

1. **Что такое списки и кортежи в Python и чем они отличаются?**
    - Списки – изменяемые последовательности элементов, кортежи – неизменяемые последовательности элементов.
2. **Как работают словари в Python и для чего они используются?**
    - Словари – это коллекции пар "ключ-значение", используются для быстрого доступа к значениям по ключам.
3. **Что такое генераторы в Python и как они работают?**
    - Генераторы – это функции, которые возвращают объект, который может итерироваться (один элемент за раз). Они используют ключевое слово `yield`.
4. **Как работает управление исключениями в Python?**
    - Управление исключениями осуществляется с помощью блоков `try`, `except`, `finally`.
5. **Что такое декораторы и для чего они используются?**
    - Декораторы – это функции, которые изменяют поведение других функций или методов, добавляя к ним функциональность.
6. **Объясните разницу между** `**deepcopy**` **и** `**copy**`**.**
    - `copy` создает поверхностную копию объекта, `deepcopy` создает полную копию объекта, включая все вложенные объекты.
7. **Что такое контекстные менеджеры и как использовать** `**with**`**?**
    - Контекстные менеджеры управляют ресурсами (например, файлами) и обеспечивают правильное их закрытие. Использование `with` обеспечивает автоматическое управление ресурсами.
8. **Как работают списковые включения (list comprehensions) в Python?**
    - Списковые включения позволяют создавать новые списки, применяя выражение к каждому элементу существующей последовательности.
9. **Как использовать модули и пакеты в Python?**
    - Модули – это файлы с расширением `.py`, содержащие Python-код. Пакеты – это директории с модулями и специальным файлом `__init__.py`.
10. **Что такое глобальные и локальные переменные в Python?**
    
    - Глобальные переменные определяются вне функций и доступны в любом месте модуля. Локальные переменные определяются внутри функций и доступны только в их пределах.
    
    ### **Вопросы Spark:**
    
    ### **Что такое Spark и опыт?**
    
    - Apache Spark — это фреймворк с открытым исходным кодом, который в основном используется для анализа Big Data, машинного обучения и обработки данных в реальном времени. Фреймворк в общем и целом обеспечивает полнофункциональный интерфейс для программистов и разработчиков – этот интерфейс отлично помогает в решении различных задач кластерного программирования и машинного обучения.**В**
    
    ### **В случае если опыт есть:**
    
    1. Расскажите архитектуру Apache Spark?
    
    - Тут важно понять lifecycle spark. Про wide and narrow трансформации. Про драйвер как запускается, тут описан в разделе **Spark Application** [https://habr.com/ru/articles/828984/](https://habr.com/ru/articles/828984/)
    
    1. **Что Такое RDD?**
        - RDD означает “Resilient Distribution Datasets”. Это операционные элементы, которые при запуске могут работать параллельно друг другу. Всего существует два известных типа RDD – распараллеленные коллекции и наборы данных Hadoop. RDD также поддерживает два типа операций – действия и трансформации.
    2. **Что Такое Неизменность (Immutability)?**
        - Как становится понятно из названия, если предмет неизменен, то он не может быть изменён после того, как он полностью создан и уже имеет значение. Этот вопрос собеседования по Apache Spark даёт вам возможность проявить активность и добавить информацию о том, что по умолчанию Spark (в качестве фреймворка) имеет такую функцию. Однако она не применима к процессам сбора данных – только для их установленных значений.
    3. **Что Такое Раздел (Partition)**
        - Разделом или **Partition** называют небольшую часть более крупных данных. Разделы основаны на **логике** – они используются в Spark для управления данными, чтобы достичь минимального обременения сети при работе.
            
            Это ещё один вопрос по Apache Spark, который позволяет вам более подробно рассказать про эту тему. Вы можете добавить, что процесс **разделения** используется для отделения ранее упомянутой небольшой части данных от более крупной части, тем самым оптимизируя скорость всей сети.
            
    4. **Для Чего Используется SparkCore?**
        - **SparkCore** — это главный движок, отвечающий за все процессы внутри Spark. Учитывая сказанное, вы, скорее всего, не будете удивлены тем, что он имеет множество важных обязанностей – мониторинг, управление памятью и хранилищем, планирование задач и многое другое.
    5. **Data Skew - как решать проблемы**
        - Есть пару паттернов, опишу позже
    6. **Сколько Менеджеров Кластера Доступны в Spark?**
        
        По умолчания есть всего **4** менеджера кластера, которые вы можете использовать в Spark. 1. Yarn 2. Standalone 3. Mesos 4. Kubernetes.
        
        Здесь тоже важная часть необходимо спросить как работает в Kuberentes
        
11. **Секция 3: Кодинг**
    
    Если кандидат решает задачу быстро то в этом случае нужно просить улучшить алгортим. Для примера если решили сортировка за O(n2) то попросить сделать лучше например за O(nlogn).
    
    1. Задача найти сумму двух чисел равных target. Для начала кандидат может решить быстро за O(n2) используя два for, в таком случае нужно попросить кандидата решить это более оптимальнее например за O(nlogn) или O(n)
        
        [https://youtrack.wildberries.ru/articles/HRDS-A-115/python-Two-sum](https://youtrack.wildberries.ru/articles/HRDS-A-115/python-Two-sum)
        
    2. [https://youtrack.wildberries.ru/articles/HRDS-A-116/python-Palindrome-Number](https://youtrack.wildberries.ru/articles/HRDS-A-116/python-Palindrome-Number)

**SQL: задача на JOIN и оконные функции**

Таблица `**customers**`:

```Java/C/C++/C#
CREATE TABLE customers (
id INT PRIMARY KEY,
name VARCHAR(100) );
```

Таблица `**orders**`:

```Java/C/C++/C#
CREATE TABLE orders (
id INT PRIMARY KEY,
customer_id INT,
order_date DATE,
amount DECIMAL(10, 2),
FOREIGN KEY (customer_id) REFERENCES customers(id)
);
```

**Вставьте несколько записей в таблицы:**

Таблица `**customers**`:

```Java/C/C++/C#
INSERT INTO customers (id, name) VALUES (1, 'Alice'), (2, 'Bob'), (3, 'Charlie');
```

Таблица `**orders**`:

```Java/C/C++/C#
INSERT INTO orders (id, customer_id, order_date, amount) VALUES
(1, 1, '2023-01-15', 100.00),
(2, 1, '2023-01-20', 150.00),
(3, 2, '2023-01-25', 200.00),
(4, 2, '2023-02-01', 250.00),
(5, 3, '2023-02-05', 300.00),
(6, 3, '2023-02-10', 350.00),
(7, 1, '2023-02-15', 400.00),
(8, 2, '2023-02-20', 450.00),
(9, 3, '2023-03-01', 500.00),
(10, 1, '2023-03-05', 550.00);
```

**Вопросы:**

1. Что будет возвращать запрос left join:

```Java/C/C++/C#
SELECT customers.id AS customer_id, customers.name, orders.id AS order_id, orders.amount

FROM customers

LEFT JOIN orders ON customers.id = orders.customer_id;
```

1. Что будет возвращать запрос inner join:

```Java/C/C++/C#
SELECT customers.id AS customer_id, customers.name, orders.id AS order_id, orders.amount
FROM customers
INNER JOIN orders ON customers.id = orders.customer_id;
```

1. Написать запрос, который возвращает сумму заказов за каждый месяц, можно использовать функцию агрегирования `SUM` и группировку по месяцу. Предположим, что у нас есть таблица `orders` с колонками `order_date` и `amount`

**Ответ:**

```Java/C/C++/C#
SELECT

    DATE_TRUNC('month', order_date) AS month,

    SUM(amount) AS total_amount

FROM

    orders

GROUP BY

    DATE_TRUNC('month', order_date)

ORDER BY

    month;
```

1. Напишите запрос, который:
2. Возвращает информацию о каждом заказе.
3. Использует оконные функции для вычисления следующих дополнительных столбцов:
    - Кумулятивная сумма заказов для каждого клиента, отсортированная по дате заказа.
    - Средняя сумма заказов для каждого клиента, отсортированная по дате заказа.
    - Номер строки для каждого заказа в рамках каждого клиента, отсортированная по дате заказа.

Ответ:

```Java/C/C++/C#
SELECT
    id,
    customer_id,
    order_date,
    amount,
    SUM(amount) OVER (PARTITION BY customer_id ORDER BY order_date) AS cumulative_sum,
    AVG(amount) OVER (PARTITION BY customer_id ORDER BY order_date) AS average_amount,
    ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY order_date) AS row_number
FROM
    orders
ORDER BY
    customer_id,
    order_date;
```

**Пояснения:**

- `SUM(amount) OVER (PARTITION BY customer_id ORDER BY order_date)`: вычисляет кумулятивную сумму заказов для каждого клиента, отсортированных по дате заказа.
- `AVG(amount) OVER (PARTITION BY customer_id ORDER BY order_date)`: вычисляет среднюю сумму заказов для каждого клиента, отсортированных по дате заказа.
- `ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY order_date)`: вычисляет номер строки для каждого заказа в рамках каждого клиента, отсортированных по дате заказа.

**SQL: задача на JOIN и оконные функции**

Таблица `**customers**`:

```Java/C/C++/C#
CREATE TABLE customers (
id INT PRIMARY KEY,
name VARCHAR(100) );
```

Таблица `**orders**`:

```Java/C/C++/C#
CREATE TABLE orders (
id INT PRIMARY KEY,
customer_id INT,
order_date DATE,
amount DECIMAL(10, 2),
FOREIGN KEY (customer_id) REFERENCES customers(id)
);
```

**Вставьте несколько записей в таблицы:**

Таблица `**customers**`:

```Java/C/C++/C#
INSERT INTO customers (id, name) VALUES (1, 'Alice'), (2, 'Bob'), (3, 'Charlie');
```

Таблица `**orders**`:

```Java/C/C++/C#
INSERT INTO orders (id, customer_id, order_date, amount) VALUES
(1, 1, '2023-01-15', 100.00),
(2, 1, '2023-01-20', 150.00),
(3, 2, '2023-01-25', 200.00),
(4, 2, '2023-02-01', 250.00),
(5, 3, '2023-02-05', 300.00),
(6, 3, '2023-02-10', 350.00),
(7, 1, '2023-02-15', 400.00),
(8, 2, '2023-02-20', 450.00),
(9, 3, '2023-03-01', 500.00),
(10, 1, '2023-03-05', 550.00);
```

**Вопросы:**

1. Что будет возвращать запрос left join:

```Java/C/C++/C#
SELECT customers.id AS customer_id, customers.name, orders.id AS order_id, orders.amount

FROM customers

LEFT JOIN orders ON customers.id = orders.customer_id;
```

1. Что будет возвращать запрос inner join:

```Java/C/C++/C#
SELECT customers.id AS customer_id, customers.name, orders.id AS order_id, orders.amount
FROM customers
INNER JOIN orders ON customers.id = orders.customer_id;
```

1. Написать запрос, который возвращает сумму заказов за каждый месяц, можно использовать функцию агрегирования `SUM` и группировку по месяцу. Предположим, что у нас есть таблица `orders` с колонками `order_date` и `amount`

**Ответ:**

```Java/C/C++/C#
SELECT

    DATE_TRUNC('month', order_date) AS month,

    SUM(amount) AS total_amount

FROM

    orders

GROUP BY

    DATE_TRUNC('month', order_date)

ORDER BY

    month;
```

1. Напишите запрос, который:
2. Возвращает информацию о каждом заказе.
3. Использует оконные функции для вычисления следующих дополнительных столбцов:
    - Кумулятивная сумма заказов для каждого клиента, отсортированная по дате заказа.
    - Средняя сумма заказов для каждого клиента, отсортированная по дате заказа.
    - Номер строки для каждого заказа в рамках каждого клиента, отсортированная по дате заказа.

Ответ:

```Java/C/C++/C#
SELECT
    id,
    customer_id,
    order_date,
    amount,
    SUM(amount) OVER (PARTITION BY customer_id ORDER BY order_date) AS cumulative_sum,
    AVG(amount) OVER (PARTITION BY customer_id ORDER BY order_date) AS average_amount,
    ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY order_date) AS row_number
FROM
    orders
ORDER BY
    customer_id,
    order_date;
```

**Пояснения:**

- `SUM(amount) OVER (PARTITION BY customer_id ORDER BY order_date)`: вычисляет кумулятивную сумму заказов для каждого клиента, отсортированных по дате заказа.
- `AVG(amount) OVER (PARTITION BY customer_id ORDER BY order_date)`: вычисляет среднюю сумму заказов для каждого клиента, отсортированных по дате заказа.
- `ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY order_date)`: вычисляет номер строки для каждого заказа в рамках каждого клиента, отсортированных по дате заказа.

  

  

Дано целое число **x**. Верните **true**, если **x** является **палиндромом**, и **false** в противном случае.

**Пример 1:**

```Java/C/C++/C#
Вход: x = 121
Выход: true
Объяснение: 121 читается как 121 слева направо и справа налево.
```

**Пример 2:**

```Java/C/C++/C#
Вход: x = -121
Выход: false
Объяснение: Слева направо читается как -121. Справа налево получается 121-. Поэтому это не палиндром.
```

**Пример 3:**

```Java/C/C++/C#
Input: x = 10
Выход: false
Объяснение: Справа налево читается как 01. Поэтому это не палиндром
```

**Ограничения:**

- `231 <= x <= 231 - 1`

  

  

**python: Two sum**

Дан массив целых чисел **nums** и целое число **target**. Верните индексы двух чисел, сумма которых равна **target**.

Вы можете предположить, что для каждого входного массива будет существовать ровно одно решение, и нельзя использовать один и тот же элемент дважды.

Вы можете вернуть ответ в любом порядке.

Ссылка на задачу в leetcode: [https://leetcode.com/problems/two-sum/description/](https://leetcode.com/problems/two-sum/description/)

**Пример 1:**

```Java/C/C++/C#
Вход: nums = [2,7,11,15], target = 9
Выход: [0,1]
Объяснение: Потому что nums[0] + nums[1] == 9, и в ответ мы возвращаем индексы [0, 1].
```

**Пример 2:**

```Java/C/C++/C#
Вход: nums = [3,2,4], target = 6
Выход: [1,2]
```

**Пример 3:**

`Вход: nums = [3,3], target = 6 Выход: [0,1]`