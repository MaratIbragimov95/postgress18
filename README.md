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
