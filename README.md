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

![](/LabW2/161/0_table.png)

1) Выберите из таблицы orders 3 самых дешевых заказа за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.

![](/LabW2/161/1.png)

```
select * from orders where status in('new','in_progress','delivery') order by sum desc limit 3;
```
2) Выберите из таблицы orders 2 самых дорогих заказов за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.

![](/LabW2/161/2.png)

```
select * from orders where status in('new','in_progress','delivery') order by sum desc limit 2;
```
### Задание №166
#### Таблица

![](/LabW2/166/0_table.png)

3) Добавьте в таблицу orders данные о новом заказе стоимостью 8000 рублей. В заказе 4 товара (products).

![](/LabW2/166/1.png)

```
insert into orders (id, products, sum) value (6, 4, 8000);
```
#### Результат:

![](/LabW2/166/1_result.png)

### Задание №167
#### Таблица

![](/LabW2/167/0_table.png)

4) Добавьте в таблицу products новый товар — «VR-очки», стоимостью 70000 рублей в количестве (count) 2 штук.
   
![](/LabW2/167/1.png)

```
insert into products (id, name, count, price) value (7, 'VR-очки', 2, 70000);
```
#### Результат:

![](/LabW2/167/1_result.png)

### Задание №172
#### Таблица

![](/LabW2/172/0_table.png)

5) В таблицу products внесли данные с ошибкой, вместо "PS5" в наименовании написали IMAC. Исправьте ошибку.

![](/LabW2/172/1.png)

```
update products set name='PS5' where id=7;
