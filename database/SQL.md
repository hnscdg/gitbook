# SQL

可以把 SQL 分为两个部分：数据操作语言 (DML) 和 数据定义语言 (DDL)。

## DML

SQL (结构化查询语言)是用于执行查询的语法。但是 SQL 语言也包含用于更新、插入和删除记录的语法。

查询和更新指令构成了 SQL 的 DML 部分：

* select - 从数据库表中获取数据
* update - 更新数据库表中的数据
* delete - 从数据库表中删除数据
* insert into - 向数据库表中插入数据

## DDL

SQL 的数据定义语言 (DDL) 部分使我们有能力创建或删除表格。我们也可以定义索引（键），规定表之间的链接，以及施加表间的约束。

SQL 中最重要的 DDL 语句:

* create database - 创建新数据库
* alter database - 修改数据库
* create table - 创建新表
* alter table - 变更（改变）数据库表
* drop table - 删除表
* create index - 创建索引（搜索键）
* drop index - 删除索引

## [database operation](https://www.w3schools.com/sql/default.asp)

1. create database
	
	> **create database database_name**

2. drop database
	> **drop database database_name**

## table operation

1. create table
	> **create table my_table( id int, name varchar(255), ... )**

2. empty all the data of table
	> **truncate table my_table**

3. drop table
	> **drop table my_table**

4. alter table

	* add column
		> alter table table_name add column_name datatype;
	* drop column
		> alter table table_name drop column column_name;
	* alter column
		> alter table table_name alter column column_name datatype;

## SQL statement

1. select
	- SELECT cloumn1, cloumn2, ... FROM table_name;
	- SELECT * FROM table_name
2. select distinct
	- SELECT DISTINCT column1,column2, ... FROM table_name;
3. select top
	- SELECT TOP number|percent column_name(S) FROM table_name WHERE condition;
4. MIN() and MAX()
	- SELECT MIN(column_name) FROM table_name WHERE condition;
	- SELECT MAX(column_name) FROM table_name WHERE condition;
5. where
	- SELECT column1, column2, ... FROM table_name WHERE condition;
6. and or not
	- SELECT column1, column2, ... FROM table_name WHERE condition1 AND condition2 AND condition3 ...;
	- SELECT column1, column2, ... FROM table_name WHERE condition1 OR condition2 OR condition3 ...;
	- SELECT column1, column2, ... FROM table_name WHERE NOT condition;
7. order by
	- SELECT column1, column2, ... FROM table_name ORDER BY column1, column2, ... ASC|DESC;
8. insert into
	- INSERT INTO table_name (column1, column2,column2, ...) values(value1,value2,value3, ...)
	- INSERT INTO table_name values(value1, value2,value3, ...)
9. null value
	- SELECT column_names FROM table_name WHERE column_name IS NULL;
	- SELECT column_names FROM table_name WHERE column_name IS NOT NULL;
10. update
	- UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition;
11. delete
	- DELETE FROM table_name WHERE condition;
	- DELETE FROM table_name
12. count() avg() sum()
	- SELECT COUNT(column_name) FROM table_name WHERE condition;
	- SELECT AVG(column_name) FROM table_name WHERE condition;
	- SELECT SUM(column_name) FROM table_name WHERE condition;
13. like
	> % The precent sign represents zero, one, or multiple charaters
	
	> _ The underscore represents a single character

	- SELECT column1, column2, ... FROM table_name WHERE COLUMNN LIKE PATTERN;
14. in
	- SELECT column_name(S) FROM table_name WHERE column_name IN (value1, value2, ...);
	- SELECT column_name(S) FROM table_name WHERE column_name IN (SELECT STATEMENT);
15. between
	- SELECT column_name(S) FROM table_name WHERE column_name BETWEEN value1 AND value2;
16. aliases
	- SELECT column_name AS ALIAS_NAME FROM table_name;
	- SELECT column_name(S) FROM table_name AS ALIAS_NAME;
17. inner join
	- SELECT column_name(S) FROM table1 INNER JOIN table2 ON table.column_name = table2.column_name;
18. left join
	- SELECT column_name(S) FROM table1 LEFT JOIN table2 ON table1.column_name = table2.column_name;
19. right join
	- SELECT column_name(S) FROM table1 RIGHT JOIN table2 ON table1.column_name = table2.column_name;
20. full outer join
	- SELECT column_name(S) FROM table1 FULL OUTER JOIN table2 ON table1.column_name = table2.column_name;
21. self join
	- SELECT column_name(S) FROM table1 T1, table2 T2 WHERE condition;
22. union
	- SELECT column_name(S) FROM table1 UNION SELECT column_name(S) FROM table2;
	- SELECT column_name(S) FROM table1 UNION ALL SELECT column_name(S) FROM table2;


``` sql
CREATE DATABASE MY_DB -- CREATE A NEW DATABASE
-- 数据库操作
CREATE DATABASE TESTDB -- CREATE A NEW DATABASE CALLED TESTDB
DROP DATABASE TESTDB -- DROP DATABASE NAMED TESTDB

-- 数据库表操作
CREATE table STUDENTS  -- CREATE A NEW table
(
	ID INT,
	FIRSTNAME VARCHAR(255),
	LASTNAME VARCHAR(255)
)

CREATE table MY_table(ID INT) -- 新建数据库表

select * from MY_table -- 查找数据库表中的数据
TRUNCATE table MY_table -- 清空数据库表中数据
DROP table MY_table -- 删除数据库表

ALTER table MY_table ADD EMAIL VARCHAR(255) -- 为my_table重新增email列
ALTER table MY_table DROP COLUMN EMAIL -- 删除my_table中的email列
ALTER table MY_table ALTER COLUMN ID VARCHAR(255) -- 更改my_table中列为ID的属性，值类型改为varchar（255）
```




