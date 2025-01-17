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
SELECT * FROM sakila.rental r ORDER BY r.rental_id DESC LIMIT 5;
```

![rental](https://github.com/biparasite/DB-12-03HW/blob/main/rental.png)

---

## Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie.

Сформируйте вывод в результат таким образом:

все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
замените буквы 'll' в именах на 'pp'.

## Ответ

```SQL
SELECT
    LOWER(first_name) AS first_name,
    REPLACE(LOWER(first_name), 'll', 'pp') AS replaced_first_name
FROM
    customer
WHERE
    (first_name = 'Kelly' OR first_name = 'Willie');
```

![KellyWelly](https://github.com/biparasite/DB-12-03HW/blob/main/KellyWelly.png)

---

Дополнительные задания (со звёздочкой\*)

Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

## Задание 5\*

Выведите Email каждого покупателя, разделив значение Email на две отдельных колонки: в первой колонке должно быть значение, указанное до @, во второй — значение, указанное после @.

### Ответ

```SQL
SELECT c.email, 
	SUBSTRING_INDEX(c.email, '@', 1) AS username,
	SUBSTRING_INDEX(c.email, '@', -1) AS domain_name
FROM sakila.customer c;
```
![substring](https://github.com/biparasite/DB-12-03HW/blob/main/substring.png)
---
