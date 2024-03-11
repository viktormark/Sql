__CREATE DATABASE databasename; :__ Створити нову базу даних.

__DROP DATABASE databasename; :__ Видалити базу даних.

__SHOW DATABASES; :__ Показати список баз даних.

__USE databasename; :__ Обрати базу даних для використання.    

__SHOW TABLES :__ показати таблиці   

__CREATE TABLE Persons (PersonID int, FirstName varchar(255) ,LastName varchar(255),City varchar(255));__ : Створити таблицю

__DROP TABLE table_name; :__ Видалити таблицю

__INSERT INTO Persons VALUES (1, 'vlad', 'lastname1', 'lviv'), (2, 'john', 'lastname2', 'paris'), (3, 'olga', 'lastname3', 'kyiv'),(4, 'viktor', 'lastname4', 'berlin'); :__ Додавання нових рядків у таблицю.

<br><br>

__SELECT * FROM table_name; :__ Вибрати всі колонкі з таблиці

| PersonID | FirstName | LastName  | City   |
| -------- | --------- | --------- | ------ |
| 1        | vlad      | lastname1 | lviv   |
| 2        | john      | lastname2 | paris  |
| 3        | olga      | lastname3 | kyiv   |
| 4        | viktor    | lastname4 | berlin |

 <br><br>
 
__DELETE FROM Persons WHERE FirstName = "viktor"; :__  видаляє "viktor" з таблиці 

|PersonID|FirstName|LastName|City|
|---|---|---|---|
|1|vlad|lastname1|lviv|
|2|john|lastname2|paris|
|3|olga|lastname3|kyiv|

<br><br>

__UPDATE Persons SET FirstName = 'Jane' WHERE PersonID = 1; :__ Оновлення існуючих даних у таблиці.

|PersonID|FirstName|LastName|City|
|---|---|---|---|
|1|Jane|lastname1|lviv|
|2|john|lastname2|paris|
|3|olga|lastname3|kyiv|
<br><br>
__ALTER TABLE table_name ADD column_name datatype; :__ Добавляє колонку в таблицю

__ALTER TABLE table_name DROP COLUMN column_name; :__ Видаляє колонку

<br><br>

__SELECT * FROM Orders__ 

|OrderID|PersonID|Product|Quantity|
|---|---|---|---|
|101|1|Product_A|3|
|102|2|Product_B|1|
|103|1|Product_C|2|
|106|8|Product_O|8|
|108|2|Product_Y|5|

<br><br>

__SELECT * FROM Persons
JOIN Orders ON Persons.PersonID = Orders.PersonID;__ : Об'єднання даних з різних таблиць за певною умовою.

|PersonID|FirstName|LastName|City|OrderID|Product|Quantity|
|---|---|---|---|---|---|---|
|1|Jane|lastName1|lviv|101|Product_A|3|
|2|john|lastName2|paris|102|Product_B|1|
|1|Jane|lastName1|lviv|103|Product_C|2|
|2|john|lastName2|paris|108|Product_y|5|

<br><br>

__SELECT * FROM Persons
right join Orders ON Persons.PersonID = Orders.PersonID; :__ повертає всі рядки з правої таблиці та відповідні рядки з лівої таблиці. Якщо в ліві таблиці немає відповідності, записується NULL.

|PersonID|FirstName|LastName|City|OrderID|PersonID|Product|Quantity|
|---|---|---|---|---|---|---|---|
|1|Jane|lastname1|lviv|101|1|Product_A|3|
|2|john|lastname2|paris|102|2|Product_B|1|
|1|Jane|lastname1|lviv|103|1|Product_C|2|
|NULL|NULL|NULL|NULL|106|8|Product_o|8|
|2|john|lastname2|paris|108|2|Product_y|5|

<br><br>

__SELECT * FROM Orders ORDER BY Quantity ; :__ Сортування результатів по заданому полю.

|OrderID|PersonID|Product|Quantity|
|---|---|---|---|
|102|2|Product_B|1|
|103|1|Product_C|2|
|101|1|Product_A|3|
|108|2|Product_Y|5|
|106|8|Product_O|8|

<br><br>

__select * from Persons where FirstName LIKE "%oh%" :__ поверне всі рядки з таблиці Persons, де ім'я (FirstName) містить підстроку "oh".

|PersonID|FirstName|LastName|City|
|---|---|---|---|
|2|john|lastname2|paris|

<br><br>

__select * from Orders LIMIT 3 :__ Обмеження кількості повернутих рядків

|OrderID|PersonID|Product|Quantity|
|---|---|---|---|
|101|1|Product_A|3|
|102|2|Product_B|1|
|103|1|Product_C|2|

<br><br>

__select count( Quantity ) from Persons__ : рахує кількість рядків
__select sum( Quantity ) from Persons__ : обчислить суму всіх значень у стовпці Quantity
