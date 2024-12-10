# Домашнее задание к занятию «SQL. Часть 1 - Козырев Р.А.»

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

### Решение 1
```sql
SELECT DISTINCT district FROM address a WHERE district LIKE 'K%a' AND district NOT LIKE '% %';
```
![image](https://github.com/user-attachments/assets/befff428-254d-4b81-a6fd-bf042a1d6a6d)


### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года **включительно** и стоимость которых превышает 10.00.

### Решение 2
```sql
SELECT * FROM payment p WHERE amount > 10 AND date(payment_date) BETWEEN '2005-06-15' AND '2005-06-18' ORDER BY  payment_date, amount ;
```
![image](https://github.com/user-attachments/assets/45988105-2143-4a4c-aa79-e84252dd26e4)


### Задание 3

Получите последние пять аренд фильмов.

### Решение 3
```sql
SELECT * FROM rental r ORDER BY rental_date DESC LIMIT 5;
```
![image](https://github.com/user-attachments/assets/45c6be7d-d353-44aa-87ce-5e3d7f223a78)


### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

### Решение 4
```sql
SELECT replace(lower(first_name), 'll', 'pp'), lower(last_name), email FROM customer c WHERE first_name = 'KELLY' OR first_name = 'WILLIE';
```
![image](https://github.com/user-attachments/assets/acbf0265-f76f-4601-9849-aefdcabdee81)
