# Домашнее задание к занятию «Базы данных»

---
### Легенда

Заказчик передал вам [файл в формате Excel](https://github.com/netology-code/sdb-homeworks/blob/main/resources/hw-12-1.xlsx), в котором сформирован отчёт. 

На основе этого отчёта нужно выполнить следующие задания.

### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

- какие данные хранятся в этих таблицах;
- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

Приведите решение к следующему виду:

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).

# Решение

```
1. Сотрудники
идентификатор: serial (первичный ключ,bigserial для больших объемов данных)
фамилия: varchar(50)
имя: varchar(50)
отчество: varchar(50)
оклад: numeric(10, 2)
должность: varchar(100)
дата_найма: date
идентификатор структурного подразделения: integer
идентификатор проекта: integer
2. Подразделения
идентификатор: serial (первичный ключ, bigserial)
наименование: varchar(100)
тип: varchar(50)
адрес: varchar(255)
3. Должности
идентификатор: serial (первичный ключ, bigserial)
наименование: varchar(100)
описание: text
4. Адреса
идентификатор: serial (первичный ключ, bigserial)
страна: varchar(100)
регион: varchar(100)
город: varchar(100)
улица: varchar(100)
дом: varchar(10)
квартира: varchar(10)
5. Заработные платы
идентификатор: serial (первичный ключ, bigserial)
идентификатор сотрудника: integer
дата_изменения: date
новая_зарплата: numeric(10, 2)
6. Отпуска
идентификатор: serial (первичный ключ, bigserial)
идентификатор сотрудника: integer
дата_начала: date
дата_окончания: date
тип_отпуска: varchar(50)
статус: varchar(50)
7. Обучение
идентификатор: serial (первичный ключ, bigserial)
идентификатор сотрудника: integer
наименование_курса: varchar(100)
дата_начала: date
дата_окончания: date
результат: varchar(50)
8. Проекты
идентификатор: serial (первичный ключ, bigserial)
название: varchar(100)
описание: text
дата_начала: date
дата_окончания: date
идентификатор структурного подразделения: integer


