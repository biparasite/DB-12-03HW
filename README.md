# Домашнее задание к занятию " `SQL. Часть 1` " - `Сулименков Алексей`

---

## Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

### Ответ

```SQL
SELECT DISTINCT district  FROM sakila.address WHERE district LIKE 'K%a' AND district NOT LIKE '% %';
```

![district](https://github.com/biparasite/DB-12-03HW/blob/main/district.png)

---

## Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.

### Ответ

```SQL
SELECT p.amount, p.payment_date FROM sakila.payment p WHERE p.amount > 10 AND CAST(p.payment_date AS DATE) BETWEEN '2005-06-15' AND '2005-06-18';
```

![amount](https://github.com/biparasite/DB-12-03HW/blob/main/amount.png)

---

## Задание 3

Получите последние пять аренд фильмов.

### Ответ

```SQL

```

---
