
# ClickHouse

![image](https://github.com/user-attachments/assets/1d7d2015-57f5-4fd3-877b-0d58546c74b2)


## Официальный канал

- [https://t.me/clickhouse_ru](https://t.me/clickhouse_ru)

## Документация

- [Официальная документация ClickHouse](https://clickhouse.com/docs/)
- [clickhouse-driver Quickstart](https://clickhouse-driver.readthedocs.io/en/latest/quickstart.html)

## Курсы

- [ClickHouse для аналитика](https://stepik.org/course/100210) (я осталась очень недовольна этим курсом, но другого просто нет)

## Песочница

- [https://fiddle.clickhouse.com](https://fiddle.clickhouse.com/)

## Как поднять ClickHouse
- https://youtu.be/W22Dp3rGkis?si=sWyHfSHaErQeMBn7
- https://youtu.be/Zla6iN7W5ns?si=KrwyqbFq46pk32EY
- https://youtu.be/I1h2YaWW9PE?si=Ei9ZXzDewsCAupHu

## Важно знать

1. Типы данных 
2. [Комбинаторные функции](https://clickhouse.com/docs/ru/sql-reference/aggregate-functions/combinators)
3. [Массивы](https://clickhouse.com/docs/en/sql-reference/functions/array-functions)
4. [map functions](https://clickhouse.com/docs/ru/sql-reference/functions/tuple-map-functions) + как работать с lambda в ClickHouse
5. [Оконные функции](https://clickhouse.com/docs/en/sql-reference/window-functions)
6. [CTE Common Table Expressions](https://clickhouse.com/docs/en/sql-reference/statements/select/with)
7. [limit by](https://clickhouse.com/docs/en/sql-reference/statements/select/limit-by)
8. [Внешние словари](https://clickhouse.com/docs/en/sql-reference/functions/ext-dict-functions)
9. [Создание таблиц](https://clickhouse.com/docs/ru/sql-reference/statements/create/table)
10. [Вставка значений](https://clickhouse.com/docs/ru/sql-reference/statements/insert-into)
11. [Удаление таблиц](https://clickhouse.com/docs/ru/sql-reference/statements/drop)
12. [Работа со строками](https://clickhouse.com/docs/en/sql-reference/functions/string-search-functions) + регулярные выражения
13. [arrayJoin](https://clickhouse.com/docs/en/sql-reference/functions/array-join)
14. [Дата и время](https://clickhouse.com/docs/en/sql-reference/functions/date-time-functions)
15. any при группировке
16. какие есть движки (+ практика создания таблиц)

  

  

  

## Полезные статьи

- [https://kb.altinity.com/altinity-kb-queries-and-syntax/](https://kb.altinity.com/altinity-kb-queries-and-syntax/)
- [https://kb.altinity.com/altinity-kb-queries-and-syntax/distinct-vs-group-by-vs-limit-by/](https://kb.altinity.com/altinity-kb-queries-and-syntax/distinct-vs-group-by-vs-limit-by/)

## Пример использования external table

```Python
external_tables = [{
	'name': 'external_table',
	'structure': [('FeedbackId', 'String')],
	'data': pandas_dataframe[['FeedbackId']].to_dict(orient='records')
}]

Q = """
	SELECT FeedbackId, proba
	FROM clickhouse_table
	WHERE FeedbackId IN external_table

	"""
	
df = db_client.query_dataframe(Q, external_tables=external_tables)
```

## Explain 
![image](https://github.com/user-attachments/assets/9bbe5831-f7e1-4581-abce-acf77c5ad470)


## Пример 
Создание таблицы: Заказы клиентов
```
CREATE TABLE orders (
    order_id UInt32,
    client_id UInt32,
    order_date DateTime,
    amount Float64,
    status String,
    items Array(String),
    details Map(String, String)
) 
ENGINE = MergeTree()
ORDER BY order_id;
```
Вставка данных
```
INSERT INTO orders (order_id, client_id, order_date, amount, status, items, details) VALUES
(1, 101, '2024-10-01 12:30:00', 2500.50, 'completed', ['laptop', 'mouse'], {'payment_method': 'credit_card', 'delivery': 'courier'}),
(2, 102, '2024-10-02 14:15:00', 1000.00, 'completed', ['smartphone'], {'payment_method': 'cash', 'delivery': 'pickup'}),
(3, 103, '2024-10-03 16:45:00', 1500.75, 'pending', ['tablet'], {'payment_method': 'credit_card', 'delivery': 'courier'}),
(4, 101, '2024-10-05 10:20:00', 300.00, 'completed', ['keyboard'], {'payment_method': 'debit_card', 'delivery': 'courier'}),
(5, 104, '2024-10-07 09:10:00', 2750.00, 'completed', ['monitor', 'headphones'], {'payment_method': 'cash', 'delivery': 'pickup'}),
(6, 102, '2024-10-08 18:50:00', 500.00, 'canceled', ['charger'], {'payment_method': 'debit_card', 'delivery': 'courier'}),
(7, 105, '2024-10-09 11:30:00', 2200.00, 'completed', ['smartwatch'], {'payment_method': 'credit_card', 'delivery': 'pickup'}),
(8, 103, '2024-10-10 13:00:00', 3400.25, 'completed', ['laptop', 'printer'], {'payment_method': 'credit_card', 'delivery': 'courier'}),
(9, 106, '2024-10-10 14:45:00', 800.00, 'pending', ['router'], {'payment_method': 'cash', 'delivery': 'pickup'}),
(10, 107, '2024-10-11 08:20:00', 150.00, 'completed', ['usb_cable'], {'payment_method': 'debit_card', 'delivery': 'courier'});
```

Описание таблицы:

1. order_id: Уникальный идентификатор заказа.
2. client_id: Идентификатор клиента, который сделал заказ.
3. order_date: Дата и время оформления заказа.
4. amount: Сумма заказа в рублях.
5. status: Статус заказа (completed, pending, canceled).
6. items: Массив товаров, содержащий названия продуктов.
7. details: Карта, содержащая дополнительные данные о заказе (например, метод оплаты и способ доставки).


---


### 1. **Комбинаторные функции**  
**Задача:**  
Используйте функцию `groupArray` для получения списка всех товаров, которые заказывал клиент с `client_id = 101`.  
**Запрос:**  
```sql
SELECT client_id, groupArray(items) AS all_items
FROM orders
WHERE client_id = 101
GROUP BY client_id;
```

---

### 2. **Массивы**  
**Задача:**  
Напишите запрос, который вернёт все заказы, где в массиве `items` содержится товар `'laptop'`.  
**Запрос:**  
```sql
SELECT *
FROM orders
WHERE has(items, 'laptop');
```

---

### 3. **map functions + lambda в ClickHouse**  
**Задача:**  
Используйте функцию `arrayMap`, чтобы получить массив товаров в верхнем регистре.  
**Запрос:**  
```sql
SELECT order_id, arrayMap(x -> upper(x), items) AS upper_items
FROM orders;
```

---

### 4. **Оконные функции**  
**Задача:**  
Найдите сумму заказов каждого клиента и укажите ранг клиента по общей сумме заказов (используйте оконную функцию).  
**Запрос:**  
```sql
SELECT client_id, 
       SUM(amount) OVER (PARTITION BY client_id) AS total_amount,
       RANK() OVER (ORDER BY SUM(amount) OVER (PARTITION BY client_id) DESC) AS rank
FROM orders;
```

---

### 5. **CTE (Common Table Expressions)**  
**Задача:**  
Создайте временную таблицу с заказами, которые были завершены, и выведите их.  
**Запрос:**  
```sql
WITH completed_orders AS (
    SELECT * FROM orders WHERE status = 'completed'
)
SELECT * FROM completed_orders;
```

---

### 6. **limit by**  
**Задача:**  
Выведите не более двух заказов для каждого клиента, используя `LIMIT BY`.  
**Запрос:**  
```sql
SELECT *
FROM orders
ORDER BY order_date DESC
LIMIT 2 BY client_id;
```

---

### 7. **Удаление таблиц**  
**Задача:**  
Удалите таблицу `orders`.  
**Запрос:**  
```sql
DROP TABLE orders;
```

---

### 8. **Работа со строками + регулярные выражения**  
**Задача:**  
Напишите запрос, который выбирает заказы, где в способе доставки встречается слово `'courier'`.  
**Запрос:**  
```sql
SELECT *
FROM orders
WHERE details['delivery'] LIKE '%courier%';
```

---

### 9. **arrayJoin**  
**Задача:**  
Используйте `arrayJoin` для получения строки с каждым товаром отдельно.  
**Запрос:**  
```sql
SELECT order_id, arrayJoin(items) AS item
FROM orders;
```

---

### 10. **Дата и время**  
**Задача:**  
Выведите все заказы, сделанные в октябре 2024 года.  
**Запрос:**  
```sql
SELECT *
FROM orders
WHERE toMonth(order_date) = 10 AND toYear(order_date) = 2024;
```

---

### 11. **any при группировке**  
**Задача:**  
Используйте `any` для получения случайного способа доставки для каждого клиента.  
**Запрос:**  
```sql
SELECT client_id, any(details['delivery']) AS random_delivery
FROM orders
GROUP BY client_id;
```
