# SQL

可以把 SQL 分为两个部分：数据操作语言 (DML) 和 数据定义语言 (DDL)。

## DML

SQL (结构化查询语言)是用于执行查询的语法。但是 SQL 语言也包含用于更新、插入和删除记录的语法。

查询和更新指令构成了 SQL 的 DML 部分：

* SELECT - 从数据库表中获取数据
* UPDATE - 更新数据库表中的数据
* DELETE - 从数据库表中删除数据
* INSERT INTO - 向数据库表中插入数据

## DDL

SQL 的数据定义语言 (DDL) 部分使我们有能力创建或删除表格。我们也可以定义索引（键），规定表之间的链接，以及施加表间的约束。

SQL 中最重要的 DDL 语句:

* CREATE DATABASE - 创建新数据库
* ALTER DATABASE - 修改数据库
* CREATE TABLE - 创建新表
* ALTER TABLE - 变更（改变）数据库表
* DROP TABLE - 删除表
* CREATE INDEX - 创建索引（搜索键）
* DROP INDEX - 删除索引

## database operation

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

## SQL STATEMENT

1. SELECT

	- SELECT CLOUMN1, COLUMN2, ... FROM TABEL_NAME;
	- SELECT * FROM TABLE_NAME
2. SELECT DISTINCT

	- SELECT DISTINCT COLUMN1,COLUMN2,... FROM TABLE_NAME;
3. SELECT TOP
	- SELECT TOP NUMBER|PERCENT COLUMN_NAME(S) FROM TABLE_NAME WHERE CONDITION;
4. MIN() ADN MAX()
	- SELECT MIN(COLUMN_NAME) FROM TABLE_NAME WHERE CONDITION;
	- SELECT MAX(COLUMN_NAME) FROM TABLE_NAME WHERE CONDITION;
5. WHERE
	- SELECT COLUMN1, COLUMN2,... FROM TABLE_NAME WHERE CONDITION;
6. AND OR NOT
	- SELECT COLUMN1, COLUMN2,... FROM TABLE_NAME WHERE CONDITION1 AND CONDITION2 AND CONDITION3 ...;
	- SELECT COLUMN1, COLUMN2, ... FROM TABLE_NAME WHERE CONDITION1 OR CONDITION2 OR CONDITION3 ...;
	- SELECT COLUMN1, COLUMN2, ... FROM TABLE_NAME WHERE NOT CONDITION;
7. ORDER BY
	- SELECT COLUMN1, COLUMN2, ... FROM TABLE_NAME ORDER BY COLUMN1, COLUMN2, ... ASC|DESC;
8. INSERT INTO
	- INSERT INTO TABLE_NAME (COLUMN1, COLUMN2,COLUMN3, ...) VALUES(VALUE1,VALUE2,VALUE3, ...)
	- INSERT INTO TABLE_NAME VALUES(VALUE1, VALUE2,VALUE3, ...)


``` sql
CREATE DATABASE MY_DB -- CREATE A NEW DATABASE
-- 数据库操作
CREATE DATABASE TESTDB -- CREATE A NEW DATABASE CALLED TESTDB
DROP DATABASE TESTDB -- DROP DATABASE NAMED TESTDB

-- 数据库表操作
CREATE TABLE STUDENTS  -- CREATE A NEW TABLE
(
	ID INT,
	FIRSTNAME VARCHAR(255),
	LASTNAME VARCHAR(255)
)

CREATE TABLE MY_TABLE(ID INT) -- 新建数据库表

select * from MY_TABLE -- 查找数据库表中的数据
TRUNCATE TABLE MY_TABLE -- 清空数据库表中数据
DROP TABLE MY_TABLE -- 删除数据库表

ALTER TABLE MY_TABLE ADD EMAIL VARCHAR(255) -- 为my_table重新增email列
ALTER TABLE MY_TABLE DROP COLUMN EMAIL -- 删除my_table中的email列
ALTER TABLE MY_TABLE ALTER COLUMN ID VARCHAR(255) -- 更改my_table中列为ID的属性，值类型改为varchar（255）
```




