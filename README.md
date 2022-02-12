# MySQL
### MySQL SHOW DATABASES Statement:
>SHOW DATABASES;
---

| Database           |
|--------------------|
| db1                |
| information_schema |
| mysql              |
| performance_schema |
| sakila             |
| school             |
| students           |
| sys                |
| visiters           |
| world              |

10 rows in set (0.00 sec)
### The MySQL USE DATABASE Statement:
>USE school;
---
### MySQL CREATE TABLE Statement;
>create table student_info(id int primary key auto_increment, name varchar(20),DOB date UNIQUE );
---
Query OK, 0 rows affected (0.04 sec)
### MySQL SHOW TABLES Statement:
>SHOW TABLES;
---
| Tables_in_school |
|------------------|
| student_info     |

1 row in set (0.00 sec)
### MySQL DESCRIBE TABLE Statement:
>DESC student_info;
```DESCRIBE student_info;```
---
| Field | Type        | Null | Key | Default | Extra          |
|-------|-------------|------|-----|---------|----------------|
| id    | int         | NO   | PRI | NULL    | auto_increment |
| name  | varchar(20) | YES  |     | NULL    |                |
| DOB   | date        | YES  | UNI | NULL    |                |

3 rows in set (0.01 sec)
### MySQL INSERT INTO Statement:
>insert into student_info values(1,"maha","2000-11-23");
```insert into student_info (name,DOB) values("pavi","2000-3-27");```
---
Query OK, 1 row affected (0.01 sec)
###  MySQL SELECT Statement:
```SELECT * FROM student_info;```
---

| id | name | DOB        |
|----|------|------------|
|  1 | maha | 2000-11-23 |
|  2 | pavi | 2000-03-27 |
|  3 | viji | 1999-08-15 |

3 rows in set (0.00 sec)
### MySQL WHERE Clause:

```SELECT * FROM student_info WHERE Id='1';```
---

| id | name | DOB        |
|----|------|------------|
|  1 | maha | 2000-11-23 |

1 row in set (0.01 sec)

### MySQL ALTER TABLE Statement :
* ADD COLUMN:
```ALTER TABLE student_info ADD age int(2);```
---
* MODIFY COLUMN:
#### syntax:
ALTER TABLE table_name
RENAME COLUMN old_name TO new_name;
```ALTER TABLE student_info RENAME COLUMN age to section ;``
* DROP COLUMN:
```alter table student_info drop section;```
### MySQL UPDATE Statement:
UPDATE statement is used to modify the existing records in a table.
```update student_info set DOB ="2000-8-18", name = "gayathri" where id = 3;```
---
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0
### MySQL DROP TABLE Statement:

### MySQL Constraints:
* NOT NULL - Ensures that a column cannot have a NULL value
* UNIQUE - Ensures that all values in a column are different
* PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
* FOREIGN KEY - Prevents actions that would destroy links between tables
* CHECK - Ensures that the values in a column satisfies a specific condition
* DEFAULT - Sets a default value for a column if no value is specified
* CREATE INDEX - Used to create and retrieve data from the database very quickly

``` create table student_info(id int auto_increment,name varchar(20) not null,DOB date unique not null, primary key(id));```

Query OK, 0 rows affected (0.04 sec)
 
#### foreign key:
``` create table mark_list(id int not null, mark int not null, section varchar(1) default 'B', foreign key (id) references student_info(id));```

Query OK, 0 rows affected (0.07 sec)
----
```insert into mark_list values(2,99,default);```

Query OK, 1 row affected (0.01 sec)
----

``` select*from mark_list;```

| id | mark | section |
|----|------|---------|
|  1 |   99 | B       |
|  2 |   99 | B       |

2 rows in set (0.00 sec)
