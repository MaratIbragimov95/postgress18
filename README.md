* `\с` - показывает в какой бд находимся и через какого юзера

* `\с` name_of_db' - переключается к этой бд

* `\dt` - показывает все таблицы в бд

* `\du` - показывает всех юзеров

* `\l` - показывает все бд 

* `\q` - выход

* `CREATE DATABASE name_of_db` = создаёт базу данных

* `CREATE TABLE name_of_table` (
    name_of_column1 type constraint,
    name_of_column2 type constraint,
    ...
); - создаёт таблицу с полями

* `INSERT INTO name_of_table (name_of_column1, name_of_column2) VALUES (val1, val2);` - добавляет запись в таблицу

* `SELECT * name_of_table;` - достаёт все поля и записи из таблицы

* `SELECT * name_of_column1, name_of_column2 from name_of_table;` - достаёт только указанные столбцы из таблицы

<!-- виды связей -->
<!-- pk and fk -->
> One to one - (один к одному)
Например:
* Один автор - одна биография
* Один флаг - одна страна
* Один человек - одно сердце

> One to many
Например:
* Один человек - много клеток, но у одной клетки только один человек
* Одни родители - много детей, но у одного ребёнка только одни родители
* Один аккаунт - много постов, но у одного поста только один аккаунт
* Один makers - много менторов, но у ментора только один makers

> Many to many
Например:
* у одного человека много друзей и у одного друга много других друзей
* у докторов много пациентов, и у пациента много докторов

<!-- Виды связей практика -->
* one to one
---sql
Create Table flag (
    id serial primary key,
    photo text)

CREATE TABLE country (
    id serial primary key,
    title varchar(50),
    gimn text,
    flag_id int unique 
    foreigh key fk_country_flag references flag(id)
);
---

* one to many
---sql
CREATE TABLE account(
    id serial primary key,
    nickname varchar(25) unique,
    u_password varchar(255)
);

CREATE TABLE post(
    id serial primary key,
    title varchar(100),
    body text, 
    photo text
    account_id int 
    foreigh key 
    fk_account_post references account(id)
);

* many to many
---sql
CREATE TABLE doctor(
    id serial primary key,
    first_name varchar(25),
    last_name varchar(50)
);

CREATE TABLE pacient(
    id serial primary key,
    first_name varchar(25),
    last_name varchar(50)
);

CREATE TABLE doctor_pacient(
    doctor_id int
    foreign key fk_doctor references doctor(id),
    pacient_id int
    foreign key fk_pacient references pacient(id)
);
