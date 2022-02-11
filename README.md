# MySQL
### MySQL SHOW DATABASES Statement:
```SHOW DATABASES;```

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
```USE school;```
### MySQL CREATE TABLE Statement;
```create table student_info(id int primary key auto_increment, name varchar(20),DOB date UNIQUE );```
Query OK, 0 rows affected (0.04 sec)
### MySQL SHOW TABLES Statement:
```SHOW TABLES;```

| Tables_in_school |
|------------------|
| student_info     |

1 row in set (0.00 sec)
### MySQL DESCRIBE TABLE Statement:
```DESC student_info;```
```DESCRIBE;```

| Field | Type        | Null | Key | Default | Extra          |
|-------|-------------|------|-----|---------|----------------|
| id    | int         | NO   | PRI | NULL    | auto_increment |
| name  | varchar(20) | YES  |     | NULL    |                |
| DOB   | date        | YES  | UNI | NULL    |                |

3 rows in set (0.01 sec)
### MySQL INSERT INTO Statement:
```insert into student_info values(1,"maha","2000-11-23");```
```insert into student_info (name,DOB) values("pavi","2000-3-27");```
Query OK, 1 row affected (0.01 sec)
###  MySQL SELECT Statement:
>SELECT * FROM student_info;

| id | name | DOB        |
|----|------|------------|
|  1 | maha | 2000-11-23 |
|  2 | pavi | 2000-03-27 |
|  3 | viji | 1999-08-15 |

3 rows in set (0.00 sec)


