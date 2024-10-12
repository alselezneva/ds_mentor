---
Категория:
  - DS-материал
---
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

## Важно знать

1. Типы данных в ClickHouse
2. комбинаторные ф [https://clickhouse.com/docs/ru/sql-reference/aggregate-functions/combinators](https://clickhouse.com/docs/ru/sql-reference/aggregate-functions/combinators)
3. массивы [https://clickhouse.com/docs/en/sql-reference/functions/array-functions](https://clickhouse.com/docs/en/sql-reference/functions/array-functions)
4. map [https://clickhouse.com/docs/ru/sql-reference/functions/tuple-map-functions](https://clickhouse.com/docs/ru/sql-reference/functions/tuple-map-functions) + как работать с lambda в ClickHouse
5. оконные ф [https://clickhouse.com/docs/en/sql-reference/window-functions](https://clickhouse.com/docs/en/sql-reference/window-functions)
6. CTE Common Table Expressions  [https://clickhouse.com/docs/en/sql-reference/statements/select/with](https://clickhouse.com/docs/en/sql-reference/statements/select/with)
7. limit by [https://clickhouse.com/docs/en/sql-reference/statements/select/limit-by](https://clickhouse.com/docs/en/sql-reference/statements/select/limit-by)
8. внешние словари [https://clickhouse.com/docs/en/sql-reference/functions/ext-dict-functions](https://clickhouse.com/docs/en/sql-reference/functions/ext-dict-functions)
9. создание таблиц [https://clickhouse.com/docs/ru/sql-reference/statements/create/table](https://clickhouse.com/docs/ru/sql-reference/statements/create/table)
10. вставка значений [https://clickhouse.com/docs/ru/sql-reference/statements/insert-into](https://clickhouse.com/docs/ru/sql-reference/statements/insert-into)
11. удаление таблиц [https://clickhouse.com/docs/ru/sql-reference/statements/drop](https://clickhouse.com/docs/ru/sql-reference/statements/drop)
12. строки [https://clickhouse.com/docs/en/sql-reference/functions/string-search-functions](https://clickhouse.com/docs/en/sql-reference/functions/string-search-functions) + регулярные выражения
13. arrayJoin [https://clickhouse.com/docs/en/sql-reference/functions/array-join](https://clickhouse.com/docs/en/sql-reference/functions/array-join)
14. даты и время [https://clickhouse.com/docs/en/sql-reference/functions/date-time-functions](https://clickhouse.com/docs/en/sql-reference/functions/date-time-functions)
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
