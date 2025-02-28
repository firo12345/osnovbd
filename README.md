## Лабораторная работа №1 [15.02.2025]
### Таблица
![0_table](https://github.com/user-attachments/assets/9ec70843-31c2-4742-a368-f7bae92ba343)


### Задание №1
Выберите из таблицы orders все заказы
![1](https://github.com/user-attachments/assets/e92c1f9b-5d9e-4897-9976-5db225f2f144)



```
SELECT * FROM orders;
```
### Задание №2
Выберите из таблицы orders все заказы кроме новых. У новых заказов status равен "new". Использовать in
![2](https://github.com/user-attachments/assets/580cf925-54ef-4cbe-8ba4-256042946a76)



```
SELECT * FROM orders WHERE status IN ('cancelled','in_progress','delivery')
```
### Задание №3
Выберите из таблицы orders все новые и отмененные заказы. У отмененных заказов status равен "cancelled". У новых заказов status равен "new"
![3](https://github.com/user-attachments/assets/903cab27-7714-47d0-8369-f1f65fa29e6c)


```
SELECT * FROM orders WHERE status = 'new' OR status = 'cancelled'
```
### Задание №4
Выберите из таблицы orders все заказы содержащие более 3 товаров (products_count).
Вывести нужно только номер (id) и сумму (sum) заказа
![4](https://github.com/user-attachments/assets/07f21f06-dfb0-4b09-a086-7bdee1eb917e)



```
SELECT id,sum FROM orders WHERE products_count > 3
```
## Лабораторная работа №2 [22.02.2025]
### Задание №161
#### Таблица
![0_table](https://github.com/user-attachments/assets/3056cc32-1fff-48a4-acca-23bd22489327)



1) Выберите из таблицы orders 3 самых дешевых заказа за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.
![1](https://github.com/user-attachments/assets/71fb6483-9f28-4efb-aa26-e9cdf7c17f56)



```
select * from orders where status in('new','in_progress','delivery') order by sum desc limit 3;
```
2) Выберите из таблицы orders 2 самых дорогих заказов за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.
![2](https://github.com/user-attachments/assets/e20082bd-539e-4ec3-8aa6-c78885885332)



```
select * from orders where status in('new','in_progress','delivery') order by sum desc limit 2;
```
### Задание №166
#### Таблица
![0_table](https://github.com/user-attachments/assets/844a0c54-3e2c-4146-9975-bcde40bd2c9b)



3) Добавьте в таблицу orders данные о новом заказе стоимостью 8000 рублей. В заказе 4 товара (products).
![1](https://github.com/user-attachments/assets/29f99c62-40ad-4974-9884-c1f4f20cf7c6)



```
insert into orders (id, products, sum) value (6, 4, 8000);
```
#### Результат:
![1_result](https://github.com/user-attachments/assets/f85a82d8-66aa-494f-a76e-90526a533937)



### Задание №167
#### Таблица
![0_table](https://github.com/user-attachments/assets/a2c43aee-ddc4-4142-b8dc-8b341dbd2b13)



4) Добавьте в таблицу products новый товар — «VR-очки», стоимостью 70000 рублей в количестве (count) 2 штук.
   ![1](https://github.com/user-attachments/assets/b3143a65-7d8d-4325-8000-35fd72f3a62b)



```
insert into products (id, name, count, price) value (7, 'VR-очки', 2, 70000);
```
#### Результат:
![1_result](https://github.com/user-attachments/assets/c628bb4a-8833-4a9b-adf0-10129980cad9)



### Задание №172
#### Таблица
![0_table](https://github.com/user-attachments/assets/2b4f03dd-9dc6-4676-a314-39bda561b9b1)



5) В таблицу products внесли данные с ошибкой, вместо "PS5" в наименовании написали IMAC. Исправьте ошибку.
![1](https://github.com/user-attachments/assets/b01951f4-1ec5-4f75-89e1-130dcd87db19)


```
update products set name='PS5' where id=7;
```
#### Результат:
![1_result](https://github.com/user-attachments/assets/59008f8b-c131-4795-aed2-7f116b57de53)
