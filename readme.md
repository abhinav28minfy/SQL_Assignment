```
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6

PS C:\Users\Minfy> psql --version
psql (PostgreSQL) 17.5
PS C:\Users\Minfy> psql -U postgres
Password for user postgres:
psql (17.5)
WARNING: Console code page (437) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

postgres=# CREATE USER abhinav_admin WITH PASSWORD "Jabbu@281308";
ERROR:  syntax error at or near ""Jabbu@281308""
LINE 1: CREATE USER abhinav_admin WITH PASSWORD "Jabbu@281308";
                                                ^
postgres=# CREATE USER abhinav_admin WITH PASSWORD 'Jabbu@281308';
CREATE ROLE
postgres=# CREATE DATABASE university_db OWNER abhinav_admin
postgres-# CREATE DATABASE university_db OWNER abhinav_admin;
ERROR:  syntax error at or near "CREATE"
LINE 2: CREATE DATABASE university_db OWNER abhinav_admin;
        ^
postgres=# GRANT ALL PRIVILEGES ON DATABASE university_db TO abhinav_admin;
ERROR:  database "university_db" does not exist
postgres=# CREATE DATABASE university_db OWNER abhinav_admin;
CREATE DATABASE
postgres=# GRANT ALL PRIVILEGES ON DATABASE university_db TO abhinav_admin;
GRANT
postgres=# \q
PS C:\Users\Minfy> psql -U abhinav_admin -d university_db
Password for user abhinav_admin:
psql (17.5)
WARNING: Console code page (437) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

university_db=> create table students(student_id INTEGER, first_name VARCHAR(50), last_name VARCHAR(50), email VARCHAR(100), date_of_birth DATE);
CREATE TABLE
university_db=> select * from students
university_db-> select * from students;
ERROR:  syntax error at or near "select"
LINE 2: select * from students;
        ^
university_db=> Select * from students;
 student_id | first_name | last_name | email | date_of_birth
------------+------------+-----------+-------+---------------
(0 rows)


university_db=> Alter table students add column enrollment_date DATE
university_db-> Select * from students;
ERROR:  syntax error at or near "Select"
LINE 2: Select * from students;
        ^
university_db=> select * from students;
 student_id | first_name | last_name | email | date_of_birth
------------+------------+-----------+-------+---------------
(0 rows)


university_db=> Alter table students add column enrollment_date DATE;
ALTER TABLE
university_db=> select * from students;
 student_id | first_name | last_name | email | date_of_birth | enrollment_date
------------+------------+-----------+-------+---------------+-----------------
(0 rows)


university_db=> Alter table students drop column enrollment_date DATE
university_db-> Alter table students drop column enrollment_date DATE;
ERROR:  syntax error at or near "DATE"
LINE 1: Alter table students drop column enrollment_date DATE
                                                         ^
university_db=> Alter table students drop column enrollment_date;
ALTER TABLE
university_db=> select * from students;
 student_id | first_name | last_name | email | date_of_birth
------------+------------+-----------+-------+---------------
(0 rows)


university_db=> Alter table students add constraint unique_email UNIQUE (email);
ALTER TABLE
university_db=> desc students;
ERROR:  syntax error at or near "desc"
LINE 1: desc students;
        ^
university_db=> desc students;
ERROR:  syntax error at or near "desc"
LINE 1: desc students;
        ^
university_db=> Desc students;
ERROR:  syntax error at or near "Desc"
LINE 1: Desc students;
        ^
university_db=> Describe students;
ERROR:  syntax error at or near "Describe"
LINE 1: Describe students;
        ^
university_db=> Describe students;
ERROR:  syntax error at or near "Describe"
LINE 1: Describe students;
        ^
university_db=> DESCRIBE studets;
ERROR:  syntax error at or near "DESCRIBE"
LINE 1: DESCRIBE studets;
        ^
university_db=> \q
PS C:\Users\Minfy> psql -U abhinav_admin -d university_db
Password for user abhinav_admin:
psql (17.5)
WARNING: Console code page (437) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

university_db=> DESCRIBE students;
ERROR:  syntax error at or near "DESCRIBE"
LINE 1: DESCRIBE students;
        ^
university_db=> BEGIN DESCRIBE students; END;
ERROR:  syntax error at or near "DESCRIBE"
LINE 1: BEGIN DESCRIBE students;
              ^
WARNING:  there is no transaction in progress
COMMIT
university_db=> BEGIN DESCRIBE students; END;
ERROR:  syntax error at or near "DESCRIBE"
LINE 1: BEGIN DESCRIBE students;
              ^
WARNING:  there is no transaction in progress
COMMIT
university_db=> select * from students
university_db-> select * from students;
ERROR:  syntax error at or near "select"
LINE 2: select * from students;
        ^
university_db=> select * from students;
 student_id | first_name | last_name | email | date_of_birth
------------+------------+-----------+-------+---------------
(0 rows)


university_db=> select * from students;
 student_id | first_name | last_name | email | date_of_birth
------------+------------+-----------+-------+---------------
(0 rows)


university_db=> Select * from students;
 student_id | first_name | last_name | email | date_of_birth
------------+------------+-----------+-------+---------------
(0 rows)


university_db=> drop table students;
DROP TABLE
university_db=> CREATE TABLE students (
university_db(>     student_id INTEGER,
university_db(>     first_name VARCHAR(50),
university_db(>     last_name VARCHAR(50),
university_db(>     email VARCHAR(100),
university_db(>     dob DATE
university_db(> );
CREATE TABLE
university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (1, 'Alice', 'Smith', 'alice.smith@example.com', '2003-05-15');
INSERT 0 1
university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (2, 'Bob', 'Johnson', 'bob.johnson@example.com', '2002-08-22'),
university_db-> Select * from students;
ERROR:  syntax error at or near "Select"
LINE 3: Select * from students;
        ^
university_db=> Select * from students;
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15
(1 row)


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob) VALUES (2, 'Bob', 'Johnson', 'bob.johnson@example.com', '2002-08-22'),
university_db-> INSERT INTO students (student_id, first_name, last_name, email, dob) (3, 'Charlie', 'Brown', 'charlie.brown@example.com', '2003-01-10');
ERROR:  syntax error at or near "INSERT"
LINE 2: INSERT INTO students (student_id, first_name, last_name, ema...
        ^
university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob) (3, 'Charlie', 'Brown', 'charlie.brown@example.com', '2003-01-10');
ERROR:  syntax error at or near "3"
LINE 1: ... (student_id, first_name, last_name, email, dob) (3, 'Charli...
                                                             ^
university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob) (3, 'Charlie', 'Brown', 'charlie.brown@example.com', '2003-01-10');
ERROR:  syntax error at or near "3"
LINE 1: ... (student_id, first_name, last_name, email, dob) (3, 'Charli...
                                                             ^
university_db=> Select * from students;
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15
(1 row)


university_db=> INSERT INTO students VALUES (2, 'Bob', 'Johnson', 'bob.johnson@example.com', '2002-08-22'),
university_db->
university_db-> INSERT INTO students VALUES (2, 'Bob', 'Johnson', 'bob.johnson@example.com', '2002-08-22'),
university_db-> Select * from students;
ERROR:  syntax error at or near "INSERT"
LINE 2: INSERT INTO students VALUES (2, 'Bob', 'Johnson', 'bob.johns...
        ^
university_db=> Select * from students;
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15
(1 row)


university_db=> INSERT INTO students VALUES (2, 'Bob', 'Johnson', 'bob.johnson@example.com', '2002-08-22'),
university_db-> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (1, 'Alice', 'Smith', 'alice.smith@example.com', '2003-05-15');
ERROR:  syntax error at or near "INSERT"
LINE 2: INSERT INTO students (student_id, first_name, last_name, ema...
        ^
university_db=>
university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (2, 'Bob', 'Johnson', 'bob.johnson@example.com', '2002-08-22'),
university_db->        (3, 'Charlie', 'Brown', 'charlie.brown@example.com', '2003-01-10');
INSERT 0 2
university_db=> select * from students;
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
(3 rows)


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (4, 'Abhinav', 'Bisht', 'abhinav.bisht@example.com', '2003-02-28');
INSERT 0 1
university_db=> select * from students;
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Abhinav    | Bisht     | abhinav.bisht@example.com | 2003-02-28
(4 rows)


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (5, 'Nikhil', 'Negi', 'nikhil.negi@example.com', '200w-12-13');
ERROR:  invalid input syntax for type date: "200w-12-13"
LINE 2: ... (5, 'Nikhil', 'Negi', 'nikhil.negi@example.com', '200w-12-1...
                                                             ^
university_db=> VALUES (5, 'Nikhil', 'Negi', 'nikhil.negi@example.com', '2002-12-13');
 column1 | column2 | column3 |         column4         |  column5
---------+---------+---------+-------------------------+------------
       5 | Nikhil  | Negi    | nikhil.negi@example.com | 2002-12-13
(1 row)


university_db=> select * from students;
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Abhinav    | Bisht     | abhinav.bisht@example.com | 2003-02-28
(4 rows)


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (5, 'Nikhil', 'Negi', 'nikhil.negi@example.com', '2002-12-13');
INSERT 0 1
university_db=> select * from students;
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Abhinav    | Bisht     | abhinav.bisht@example.com | 2003-02-28
          5 | Nikhil     | Negi      | nikhil.negi@example.com   | 2002-12-13
(5 rows)


university_db=> select first_name, last_name from students;
 first_name | last_name
------------+-----------
 Alice      | Smith
 Bob        | Johnson
 Charlie    | Brown
 Abhinav    | Bisht
 Nikhil     | Negi
(5 rows)


university_db=> select * from students where student_id=1;
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15
(1 row)


university_db=> select * from students where dob like 2003*
university_db-> select * from students where dob like 2003*;
ERROR:  syntax error at or near "select"
LINE 2: select * from students where dob like 2003*;
        ^
university_db=> select * from students where dob like 2003*;
ERROR:  syntax error at or near ";"
LINE 1: select * from students where dob like 2003*;
                                                   ^
university_db=> select * from students where dob like '2003*';
ERROR:  operator does not exist: date ~~ unknown
LINE 1: select * from students where dob like '2003*';
                                         ^
HINT:  No operator matches the given name and argument types. You might need to add explicit type casts.
university_db=> select * from students where name like '*li*';
ERROR:  column "name" does not exist
LINE 1: select * from students where name like '*li*';
                                     ^
university_db=> select * from students where first_name like '*li*';
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> select * from students where first_name like '%li%';
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com   | 2003-05-15
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
(2 rows)


university_db=> SELECT * FROM students WHERE dob BETWEEN '2002-01-01' AND '2002-12-31';
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com | 2002-08-22
          5 | Nikhil     | Negi      | nikhil.negi@example.com | 2002-12-13
(2 rows)


university_db=> select * from students where student_id=2;
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com | 2002-08-22
(1 row)


university_db=> select * from students where dob>'2003-01-1';
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com   | 2003-05-15
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Abhinav    | Bisht     | abhinav.bisht@example.com | 2003-02-28
(3 rows)


university_db=> select * from students where first_name LIKE 'B%' OR first_name LIKE 'C%';
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
(2 rows)


university_db=> select * from students where email LIKE '%.example.com';
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> select * from students where email LIKE '%@example.com';
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Abhinav    | Bisht     | abhinav.bisht@example.com | 2003-02-28
          5 | Nikhil     | Negi      | nikhil.negi@example.com   | 2002-12-13
(5 rows)


university_db=> select * from students where email LIKE is NULL;
ERROR:  syntax error at or near "NULL"
LINE 1: select * from students where email LIKE is NULL;
                                                   ^
university_db=> select * from students where email LIKE is NULL;
ERROR:  syntax error at or near "NULL"
LINE 1: select * from students where email LIKE is NULL;
                                                   ^
university_db=> select * from students where email LIKE IS NULL;
ERROR:  syntax error at or near "NULL"
LINE 1: select * from students where email LIKE IS NULL;
                                                   ^
university_db=> select * from students where email LIKE IS NULL;
ERROR:  syntax error at or near "NULL"
LINE 1: select * from students where email LIKE IS NULL;
                                                   ^
university_db=> SELECT * FROM students WHERE email IS NULL;
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> Select * FROM students WHERE email IS NULL;
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> select * FROM students WHERE email IS NULL;
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> select * FROM students WHERE email is NULL;
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> select * FROM students WHERE email IS null;
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> select * FROM students where email is null;
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> UPDATE students
university_db-> SET email = 'alices@example.net'
university_db-> WHERE student_id = 1;
UPDATE 1
university_db=> select * FROM students where email is null;
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> Select * FROM students;
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Abhinav    | Bisht     | abhinav.bisht@example.com | 2003-02-28
          5 | Nikhil     | Negi      | nikhil.negi@example.com   | 2002-12-13
          1 | Alice      | Smith     | alices@example.net        | 2003-05-15
(5 rows)


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (5, 'Eve', 'Smith', 'eve.smith@example.com', '2004-07-01');
INSERT 0 1
university_db=> SELECT DISTINCT last_name, first_name FROM students;
 last_name | first_name
-----------+------------
 Bisht     | Abhinav
 Negi      | Nikhil
 Smith     | Eve
 Smith     | Alice
 Brown     | Charlie
 Johnson   | Bob
(6 rows)


university_db=> select distict last_name, first_name from students;
ERROR:  column "distict" does not exist
LINE 1: select distict last_name, first_name from students;
               ^
university_db=> select distinct last_name, first_name from students;
 last_name | first_name
-----------+------------
 Bisht     | Abhinav
 Negi      | Nikhil
 Smith     | Eve
 Smith     | Alice
 Brown     | Charlie
 Johnson   | Bob
(6 rows)


university_db=> select distinct last_name from students;
 last_name
-----------
 Smith
 Negi
 Johnson
 Brown
 Bisht
(5 rows)


university_db=> select count(*) total_students from students;
 total_students
----------------
              6
(1 row)


university_db=> select min(dob) youngest from students;
  youngest
------------
 2002-08-22
(1 row)


university_db=> select min(dob) oldest from students;
   oldest
------------
 2002-08-22
(1 row)


university_db=> select max(dob) oldest from students;
   oldest
------------
 2004-07-01
(1 row)


university_db=> select last_name, count(*) number_of_students from students group by last_name having count(*)>1 order by number_of_students
university_db-> select last_name, count(*) number_of_students from students group by last_name having count(*)>1 order by number_of_students;
ERROR:  syntax error at or near "select"
LINE 2: select last_name, count(*) number_of_students from students ...
        ^
university_db=> select last_name, count(*) number_of_students from students group by last_name having count(*)>1 order by number_of_students;
 last_name | number_of_students
-----------+--------------------
 Smith     |                  2
(1 row)


university_db=> select distinct first_name from students;
 first_name
------------
 Nikhil
 Eve
 Alice
 Bob
 Charlie
 Abhinav
(6 rows)


university_db=> select count(*) from students group by extract(year from dob);
 count
-------
     3
     2
     1
(3 rows)


university_db=> DROP TABLE IF EXISTS students; -- Start fresh
DROP TABLE
university_db=>
university_db=> CREATE TABLE students (
university_db(>     student_id SERIAL PRIMARY KEY,  -- student_id is now PK, auto-incrementing, NOT NULL
university_db(>     first_name VARCHAR(50) NOT NULL,
university_db(>     last_name VARCHAR(50) NOT NULL,
university_db(>     email VARCHAR(100) UNIQUE,      -- Email should be unique; can be NULL unless NOT NULL is added
university_db(>     dob DATE,
university_db(>     enrollment_status VARCHAR(20) CHECK (enrollment_status IN ('enrolled', 'graduated', 'dropped', 'pending'))
university_db(> );
CREATE TABLE
university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Alice', 'Smith', 'alice.smith@example.com', '2003-05-15', 'enrolled');
INSERT 0 1
university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Robert', 'Johnson', 'robert.j@example.com', '2002-08-22', 'enrolled');
INSERT 0 1
university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Charlie', 'Brown', 'charlie.brown@example.com', '2003-01-10', 'pending');
INSERT 0 1
university_db=>
university_db=> SELECT * FROM students;
 student_id | first_name | last_name |           email           |    dob     | enrollment_status
------------+------------+-----------+---------------------------+------------+-------------------
          1 | Alice      | Smith     | alice.smith@example.com   | 2003-05-15 | enrolled
          2 | Robert     | Johnson   | robert.j@example.com      | 2002-08-22 | enrolled
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10 | pending
(3 rows)


university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Alice', 'Smith', 'alice.smith@example.com', '2003-05-15', 'enrolled');
ERROR:  duplicate key value violates unique constraint "students_email_key"
DETAIL:  Key (email)=(alice.smith@example.com) already exists.
university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Robert', 'Johnson', 'robert.j@example.com', '2002-08-22', 'enrolled');
ERROR:  duplicate key value violates unique constraint "students_email_key"
DETAIL:  Key (email)=(robert.j@example.com) already exists.
university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Charlie', 'Brown', 'charlie.brown@example.com', '2003-01-10', 'pending');
ERROR:  duplicate key value violates unique constraint "students_email_key"
DETAIL:  Key (email)=(charlie.brown@example.com) already exists.
university_db=>
university_db=> create table cources(course_id serial primary key,
university_db(> course_name varchar(100) not null unique,
university_db(> credits integer check (credits>0 and credits<10));
CREATE TABLE
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Introduction to SQL', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Introduc...
                    ^
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Database Design', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Database...
                    ^
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Web Development', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Web Deve...
                    ^
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Data Structures', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Data Str...
                    ^
university_db=>
university_db=> drop table cources
university_db-> drop table cources;
ERROR:  syntax error at or near "drop"
LINE 2: drop table cources;
        ^
university_db=> drop table cources;
DROP TABLE
university_db=> CREATE TABLE courses (
university_db(>     course_id SERIAL PRIMRY KEY,
university_db(>     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(>     credits INTEGER CHECK (credits > 0 AND credits < 10) -- Example of CHECK
university_db(> );
ERROR:  syntax error at or near "PRIMRY"
LINE 2:     course_id SERIAL PRIMRY KEY,
                             ^
university_db=>
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Introduction to SQL', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Introduc...
                    ^
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Database Design', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Database...
                    ^
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Web Development', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Web Deve...
                    ^
university_db=> CREATE TABLE courses (
university_db(>     course_id SERIAL PRIMRY KEY,
university_db(>     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(>     credits INTEGER CHECK (credits > 0 AND credits < 10) -- Example of CHECK
university_db(> );
ERROR:  syntax error at or near "PRIMRY"
LINE 2:     course_id SERIAL PRIMRY KEY,
                             ^
university_db=>
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Introduction to SQL', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Introduc...
                    ^
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Database Design', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Database...
                    ^
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Web Development', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Web Deve...
                    ^
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Data Structures', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Data Str...
                    ^
university_db=> select * from courses;
ERROR:  relation "courses" does not exist
LINE 1: select * from courses;
                      ^
university_db=> select * from courses;
ERROR:  relation "courses" does not exist
LINE 1: select * from courses;
                      ^
university_db=> select * from cources;
ERROR:  relation "cources" does not exist
LINE 1: select * from cources;
                      ^
university_db=> drop table courses;
ERROR:  table "courses" does not exist
university_db=> drop table cources;
ERROR:  table "cources" does not exist
university_db=> drop table cource;
ERROR:  table "cource" does not exist
university_db=> drop table course;
ERROR:  table "course" does not exist
university_db=> CREATE TABLE courses (
university_db(>     course_id SERIAL PRIMRY KEY,
university_db(>     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(>     credits INTEGER CHECK (credits > 0 AND credits < 10) -- Example of CHECK
university_db(> );
ERROR:  syntax error at or near "PRIMRY"
LINE 2:     course_id SERIAL PRIMRY KEY,
                             ^
university_db=> CREATE TABLE courses (
university_db(>     course_id SERIAL PRIMRY KEY,
university_db(>     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(>     credits INTEGER CHECK (credits > 0 AND credits < 10) -- Example of CHECK
university_db(> );
ERROR:  syntax error at or near "PRIMRY"
LINE 2:     course_id SERIAL PRIMRY KEY,
                             ^
university_db=> );CREATE TABLE courses (
ERROR:  syntax error at or near ")"
LINE 1: );
        ^
university_db(>     course_id SERIAL PRIMRY KEY,
university_db(>     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(>     credits INTEGER CHECK (credits > 0 AND credits < 10) -- Example of CHECK
university_db(>     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(>
university_db(>
university_db(>
university_db(> drop table course;
university_db(> drop table course;
university_db(> CREATE TABLE courses (
university_db(> CREATE TABLE courses (\c
You are now connected to database "university_db" as user "abhinav_admin".
university_db(> select * from cources
university_db(> select * from cources;
university_db(> select * from cources);
university_db(> \q
PS C:\Users\Minfy> psql -U abhinav_admin -d university_db
Password for user abhinav_admin:
psql (17.5)
WARNING: Console code page (437) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

university_db=> drop table courses;
ERROR:  table "courses" does not exist
university_db=> drop table cources;
ERROR:  table "cources" does not exist
university_db=> CREATE TABLE courses (
university_db(>     course_id SERIAL PRIMRY KEY,
university_db(>     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(>     credits INTEGER CHECK (credits > 0 AND credits < 10) -- Example of CHECK
university_db(> );
ERROR:  syntax error at or near "PRIMRY"
LINE 2:     course_id SERIAL PRIMRY KEY,
                             ^
university_db=> CREATE TABLE courses (
university_db(>     course_id SERIAL PRIMARY KEY,
university_db(>     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(>     credits INTEGER CHECK (credits > 0 AND credits < 10)
university_db(> );
CREATE TABLE
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Introduction to SQL', 3);
INSERT 0 1
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Database Design', 4);
INSERT 0 1
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Web Development', 3);
INSERT 0 1
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Data Structures', 4);
INSERT 0 1
university_db=> select * from courses;
 course_id |     course_name     | credits
-----------+---------------------+---------
         1 | Introduction to SQL |       3
         2 | Database Design     |       4
         3 | Web Development     |       3
         4 | Data Structures     |       4
(4 rows)


university_db=> CREATE TABLE enrollments (
university_db(>     enrollment_id SERIAL PRIMARY KEY,
university_db(>     student_id INTEGER NOT NULL,
university_db(>     course_id INTEGER NOT NULL,
university_db(>     enrollment_date DATE DEFAULT CURRENT_DATE, -- Sets default if not specified
university_db(>     grade CHAR(1) CHECK (grade IN ('A', 'B', 'C', 'D', 'F', 'W', NULL)),
university_db(> CONSTRAINT fk_student
university_db(>         FOREIGN KEY (student_id)
university_db(>         REFERENCES students(student_id)
university_db(>         ON DELETE CASCADE,
university_db(> CONSTRAINT fk_course
university_db(>         FOREIGN KEY (course_id)
university_db(>         REFERENCES courses(course_id)
university_db(>         ON DELETE RESTRICT,
university_db(> UNIQUE (student_id, course_id)
university_db(> );
CREATE TABLE
university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (1, 1, 'A');
INSERT 0 1
university_db=> INSERT INTO enrollments (student_id, course_id) VALUES (1, 2); -- Grade will be NULL
INSERT 0 1
university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (2, 1, 'B');
INSERT 0 1
university_db=> select * from enrollments;
 enrollment_id | student_id | course_id | enrollment_date | grade
---------------+------------+-----------+-----------------+-------
             1 |          1 |         1 | 2025-05-30      | A
             2 |          1 |         2 | 2025-05-30      |
             3 |          2 |         1 | 2025-05-30      | B
(3 rows)


university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (999, 1, '999');
ERROR:  value too long for type character(1)
university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (999, 1, 'a');
ERROR:  insert or update on table "enrollments" violates foreign key constraint "fk_student"
DETAIL:  Key (student_id)=(999) is not present in table "students".
university_db=> INSERT INTO courses (course_name, credits) VALUES ('1', 4);
INSERT 0 1
university_db=> delete from courses (course_name, credits) where course_name='1'
university_db-> delete from courses (course_name, credits) where course_name='1';
ERROR:  syntax error at or near "("
LINE 1: delete from courses (course_name, credits) where course_name...
                            ^
university_db=> delete from courses where course_name='1';
DELETE 1
university_db=> select * from courses;
 course_id |     course_name     | credits
-----------+---------------------+---------
         1 | Introduction to SQL |       3
         2 | Database Design     |       4
         3 | Web Development     |       3
         4 | Data Structures     |       4
(4 rows)


university_db=> INSERT INTO enrollments (student_id, student_id, grade) VALUES (999, 999, 'a');
ERROR:  column "student_id" specified more than once
LINE 1: INSERT INTO enrollments (student_id, student_id, grade) VALU...
                                             ^
university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (999, 999, 'a');
ERROR:  insert or update on table "enrollments" violates foreign key constraint "fk_student"
DETAIL:  Key (student_id)=(999) is not present in table "students".
university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (1, 1, 'A');
ERROR:  duplicate key value violates unique constraint "enrollments_student_id_course_id_key"
DETAIL:  Key (student_id, course_id)=(1, 1) already exists.
university_db=> INSERT INTO enrollments (student_id, course_id) VALUES (1, 2);
ERROR:  duplicate key value violates unique constraint "enrollments_student_id_course_id_key"
DETAIL:  Key (student_id, course_id)=(1, 2) already exists.
university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (2, 1, 'B');
ERROR:  duplicate key value violates unique constraint "enrollments_student_id_course_id_key"
DETAIL:  Key (student_id, course_id)=(2, 1) already exists.
university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (2, 1, 'B');
ERROR:  duplicate key value violates unique constraint "enrollments_student_id_course_id_key"
DETAIL:  Key (student_id, course_id)=(2, 1) already exists.
university_db=> select * from enrollments;
 enrollment_id | student_id | course_id | enrollment_date | grade
---------------+------------+-----------+-----------------+-------
             1 |          1 |         1 | 2025-05-30      | A
             2 |          1 |         2 | 2025-05-30      |
             3 |          2 |         1 | 2025-05-30      | B
(3 rows)


university_db=> truncate enrollments;
TRUNCATE TABLE
university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (1, 1, 'A');
INSERT 0 1
university_db=> INSERT INTO enrollments (student_id, course_id) VALUES (1, 2);
INSERT 0 1
university_db=> select * from enrollments;
 enrollment_id | student_id | course_id | enrollment_date | grade
---------------+------------+-----------+-----------------+-------
            10 |          1 |         1 | 2025-05-30      | A
            11 |          1 |         2 | 2025-05-30      |
(2 rows)


university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (2, 1, 'B');
INSERT 0 1
university_db=> select * from enrollments;
 enrollment_id | student_id | course_id | enrollment_date | grade
---------------+------------+-----------+-----------------+-------
            10 |          1 |         1 | 2025-05-30      | A
            11 |          1 |         2 | 2025-05-30      |
            12 |          2 |         1 | 2025-05-30      | B
(3 rows)


university_db=> SELECT * FROM students WHERE student_id = 1;SELECT * FROM enrollments WHERE student_id = 1;DELETE FROM students WHERE student_id = 1;
 student_id | first_name | last_name |          email          |    dob     | enrollment_status
------------+------------+-----------+-------------------------+------------+-------------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15 | enrolled
(1 row)


 enrollment_id | student_id | course_id | enrollment_date | grade
---------------+------------+-----------+-----------------+-------
            10 |          1 |         1 | 2025-05-30      | A
            11 |          1 |         2 | 2025-05-30      |
(2 rows)


DELETE 1
university_db=> SELECT * FROM students WHERE student_id = 1;
 student_id | first_name | last_name | email | dob | enrollment_status
------------+------------+-----------+-------+-----+-------------------
(0 rows)


university_db=>
```