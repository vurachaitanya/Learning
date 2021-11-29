## Postgres database

### Postgres Server Install on Ubuntu
 
 - `sudo apt install postgresql` - Install Postgres
 - `sudo -u postgres psql template1` - Connect to template1 DB which is already there
- [Configuring Postgres](https://ubuntu.com/server/docs/databases-postgresql)
 
 ### Database commands
 
 - `su - postgres` - Connect to Postgres user
 - `createdb testdb` - Create testdb database
 - `psql testdb` - Connect to testdb
 - `\help <command_name>` - Help command
 - [Syntax](https://www.tutorialspoint.com/postgresql/postgresql_syntax.htm)
 - `createdb -h localhost -p 5432 -U postgres testdb` create database from remote.
 - `\l` - List all the DB created already
 - `\q` - Quits out of that database 
 - `\c testdb;` Connect to the testdb
 - ` \conninfo` Connection information of database,table,port etc.
 - `psql -h localhost -p 5432 -U postgress testdb` from OS shell
 - Create sample database
 ```
 CREATE TABLE COMPANY(
   ID INT PRIMARY KEY     NOT NULL,
   NAME           TEXT    NOT NULL,
   AGE            INT     NOT NULL,
   ADDRESS        CHAR(50),
   SALARY         REAL
);
 ```
 - `\d` and `\d company` list all and list company database
 - schema is a named collection of tables. A schema can also contain views, indexes, sequences, data types, operators, and functions.
 - `create schema myschema;` - Create Schema
 - Create table in a schema 
 ```
 create table myschema.company(
   ID   INT              NOT NULL,
   NAME VARCHAR (20)     NOT NULL,
   AGE  INT              NOT NULL,
   ADDRESS  CHAR (25),
   SALARY   DECIMAL (18, 2),
   PRIMARY KEY (ID)
);
 ```
 - `select * from myschema.company;` - select table from a schema
 - `DROP SCHEMA myschema;` - Drop empty schema
 - `DROP SCHEMA myschema CASCADE;` - drop all objects and schema at once.
 - `INSERT INTO COMPANY (ID,NAME,AGE,ADDRESS,SALARY,JOIN_DATE) VALUES (1, 'Paul', 32, 'California', 20000.00,'2001-07-13');
` - Insert command to the company table.
- `INSERT INTO COMPANY (ID,NAME,AGE,ADDRESS,JOIN_DATE) VALUES (2, 'Allen', 25, 'Texas', '2007-12-13');
` - Second way.
- `SELECT * FROM table_name;` Get all columns from a table.


- Create table and load dummy data
```
CREATE TABLE chaitu_table (
  id SERIAL UNIQUE NOT NULL,
  code VARCHAR(10) NOT NULL, -- not unique
  article TEXT,
  name TEXT NOT NULL, -- not unique
  department VARCHAR(4),
  UNIQUE (code, department)
);

insert into chaitu_table (
    code, article, name, department
)
select
    left(md5(i::text), 10),
    md5(random()::text),
    md5(random()::text),
    left(md5(random()::text), 4)
from generate_series(1, 1000) s(i)


```
