---
# Домашнє завдання до Теми 7. Додаткові вбудовані SQL функції. Робота з часом

## 1. Напишіть SQL-запит, який для таблиці `orders` з атрибута `date` витягує рік, місяць і число. Виведіть на екран їх у три окремі атрибути поряд з атрибутом `id` та оригінальним атрибутом `date` (всього вийде 5 атрибутів).

~~~~sql
SELECT
    id,
    date,
    YEAR(date)  AS year,
    MONTH(date) AS month,
    DAY(date)   AS day
FROM orders;
~~~~

![separated year, month, day](https://github.com/oslippy/goit-rdb-hw-07/blob/main/Screenshot%202026-04-19%20at%2016.21.11.png)

