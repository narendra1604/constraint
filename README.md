# constraint
not null,primary and foreign key

Setting environment for using XAMPP for Windows.
karan@PRAVEEN c:\xampp
# mysql.exe -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 12
Server version: 10.4.25-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| lapak              |
| mysql              |
| nari               |
| performance_schema |
| phpmyadmin         |
| prav               |
| praveen            |
| test               |
+--------------------+
9 rows in set (0.001 sec)

MariaDB [(none)]> create database amar;
Query OK, 1 row affected (0.001 sec)

MariaDB [(none)]> use amar;
Database changed
MariaDB [amar]> create table employee(employee_id int primary key,first_name varchar(90),last_name varchar(90));
Query OK, 0 rows affected (0.024 sec)

MariaDB [amar]> desc employee;
+-------------+-------------+------+-----+---------+-------+
| Field       | Type        | Null | Key | Default | Extra |
+-------------+-------------+------+-----+---------+-------+
| employee_id | int(11)     | NO   | PRI | NULL    |       |
| first_name  | varchar(90) | YES  |     | NULL    |       |
| last_name   | varchar(90) | YES  |     | NULL    |       |
+-------------+-------------+------+-----+---------+-------+
3 rows in set (0.013 sec)
MariaDB [amar]> create table employes(employee_id int primary key,first_name varchar(90) NOT NULL,last_name varchar(90) NOT NULL);
Query OK, 0 rows affected (0.024 sec)

MariaDB [amar]> desc employes;
+-------------+-------------+------+-----+---------+-------+
| Field       | Type        | Null | Key | Default | Extra |
+-------------+-------------+------+-----+---------+-------+
| employee_id | int(11)     | NO   | PRI | NULL    |       |
| first_name  | varchar(90) | NO   |     | NULL    |       |
| last_name   | varchar(90) | NO   |     | NULL    |       |
+-------------+-------------+------+-----+---------+-------+
3 rows in set (0.011 sec)
MariaDB [amar]> create table department(dept_id int primary key,dept_name varchar(90));
Query OK, 0 rows affected (0.023 sec)

MariaDB [amar]> desc department;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| dept_id   | int(11)     | NO   | PRI | NULL    |       |
| dept_name | varchar(90) | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
2 rows in set (0.014 sec)

MariaDB [amar]> create table employer(emp_id int(90) primary key,firt_name varchar(90) not null,last_name varchar(90) not null,department_id int,foreign key (department_id) REFERENCES department(dept_id));
Query OK, 0 rows affected (0.026 sec)

MariaDB [amar]> desc employer;
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| emp_id        | int(90)     | NO   | PRI | NULL    |       |
| firt_name     | varchar(90) | NO   |     | NULL    |       |
| last_name     | varchar(90) | NO   |     | NULL    |       |
| department_id | int(11)     | YES  | MUL | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
4 rows in set (0.017 sec)
