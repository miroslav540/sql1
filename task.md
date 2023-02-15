# ЗАДАНИЕ
1. Создайте таблицу с мобильными телефонами, используя графический интерфейс. Необходимые поля таблицы: product_name (название товара), manufacturer (производитель), product_count (количество), price (цена). Заполните БД произвольными данными.
2. Напишите SELECT-запрос, который выводит название товара, производителя и цену для товаров, количество которых превышает 2
3. Выведите SELECT-запросом весь ассортимент товаров марки “Samsung”
4.  С помощью SELECT-запроса с оператором LIKE / REGEXP найти:
4. *  Товары, в которых есть упоминание "Iphone"
4.  * Товары, в которых есть упоминание "Samsung"
4.  * Товары, в названии которых есть ЦИФРЫ
4.  * Товары, в названии которых есть ЦИФРА "8"

## ПРОЦЕСС РАБОТЫ
---
### 1 СОЗДАНИЕ СХЕМЫ
>CREATE SCHEMA 'homework1';
### 2 СОЗДАНИЕ ТАБЛИЦЫ 
CREATE TABLE phone
>( 
    phone_id INTEGER PRIMARY KEY AUTO_INCREMENT,
    product_name VARCHAR(50),
    manufacturer VARCHAR(30),
    product_count INTEGER,
>    price DECIMAL
>);
### 3 ЗАПОЛНЕНИЕ ТАБЛИЦЫ
>INSERT INTO mobile_phone
	(product_name, manufacturer, product_count, price)
VALUES
    ('Galaxy A23', 'Samsung', 50 ,15000),
    ('iPhone 14', 'Apple', 100, 80999),
    ('A53', 'Samsung', 30, 25000),
###  SELECT-запрос, который выводит название товара, производителя и цену для товаров, количество которых превышает 2
>SELECT 
    product_name as 'Название товара',
    manufacturer as 'Производитель',
    price as 'Цена'
FROM mobile_phone
WHERE product_count >2;
### Выводим SELECT-запросом весь ассортимент товаров марки “Samsung”
>SELECT * FROM mobile_phone
WHERE manufacturer = 'Samsung'
### С помощью SELECT-запроса с оператором LIKE / REGEXP найти товары, в которых есть упоминание "Iphone"
>SELECT * FROM mobile_phone
WHERE product_name LIKE 'iPhone%';
### С помощью SELECT-запроса с оператором LIKE / REGEXP найти товары, в которых есть упоминание "Samsung"
>SELECT * FROM mobile_phone
WHERE manufacturer LIKE 'Samsung';
### С помощью SELECT-запроса с оператором LIKE / REGEXP найти товары, в названии которых есть ЦИФРЫ
>SELECT * FROM mobile_phone
WHERE product_name REGEXP '[[:digit:]]';
### С помощью SELECT-запроса с оператором LIKE / REGEXP найти товары, в названии которых есть ЦИФРА "8"
>SELECT * FROM mobile_phone
WHERE product_name REGEXP '[8]';
