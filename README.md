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

## 2. Напишіть SQL-запит, який для таблиці orders до атрибута `date` додає один день. На екран виведіть атрибут `id`, оригінальний атрибут `date` та результат додавання.

~~~~sql
SELECT
    id,
    date,
    DATE_ADD(date, INTERVAL 1 DAY) AS date_plus_one
FROM orders;
~~~~

![date plus one day](https://github.com/oslippy/goit-rdb-hw-07/blob/main/Screenshot%202026-04-19%20at%2016.25.32.png)

## 3. Напишіть SQL-запит, який для таблиці `orders` для атрибута `date` відображає кількість секунд з початку відліку (показує його значення `timestamp`). Для цього потрібно знайти та застосувати необхідну функцію. На екран виведіть атрибут `id`, оригінальний атрибут `date` та результат роботи функції.

~~~~sql
SELECT
    id,
    date,
    UNIX_TIMESTAMP(date) AS timestamp_seconds
FROM orders;
~~~~

![date to unixtime](https://github.com/oslippy/goit-rdb-hw-07/blob/main/Screenshot%202026-04-19%20at%2016.30.45.png)

## 4. Напишіть SQL-запит, який рахує, скільки таблиця `orders` містить рядків з атрибутом `date` у межах між 1996-07-10 00:00:00 та 1996-10-08 00:00:00.

~~~~sql
SELECT COUNT(*) AS orders_count
FROM orders
WHERE UNIX_TIMESTAMP(date) BETWEEN UNIX_TIMESTAMP('1996-07-10 00:00:00')
                                AND UNIX_TIMESTAMP('1996-10-08 00:00:00');
~~~~

![orders count](https://github.com/oslippy/goit-rdb-hw-07/blob/main/Screenshot%202026-04-19%20at%2016.35.31.png)
