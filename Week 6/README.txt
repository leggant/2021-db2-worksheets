To use this in sqlite
This is assuming the .sql files are the same directory that you want the sqlite database
NB the greater-than character ">" indicates a prompt - do not type this. Start in your CLI.

1) create the database:
> sqlite3.exe student.sqlite

2) Read in the schema file
> .read student-schema.sql

3) read in the data file
> .read student-data.sql

4) confirm that the tables are created
> .tables

5) check the data exists in the tables
> select * from ITP;
> select * from Student;
> select * from Apply;


INSERT INTO student values (432,'Kevin', null, 1500);
INSERT INTO student values (321,'Lori', null, 2500);
Select sID, sName, GPA From Student Where GPA > 3.5;
Select sID, sName, GPA From Student Where GPA <= 3.5;
Select sID, sName, GPA From Student Where GPA <= 3.5 OR GPA > 3.5;
Select sID, sName, GPA From Student Where GPA <= 3.5 OR GPA > 3.5 OR GPA IS NULL;


Optional: refining NULL values in SQLite (previously displayed empty): 
.nullvalue NULL
.mode column
.headers on

Select * from student where GPA is not null;
Select count(*) from student where GPA is not null;
Select * from student where GPA is null;
Select count(*) from student where GPA is null;
Select distinct GPA from student;
Select count(distinct gpa) from student;

INSERT INTO itp VALUES ('Matatini', 'Otago', NULL);

SELECT * FROM student WHERE sid NOT IN (SELECT DISTINCT sid FROM apply);
SELECT sid, 'Matatini', 'Dairy', null FROM student WHERE sid NOT IN (SELECT DISTINCT sid FROM apply);
INSERT into APPLY SELECT sid, 'Matatini', 'Dairy', null FROM student WHERE sid NOT IN (SELECT DISTINCT sid FROM apply);
SELECT * FROM apply WHERE major = 'Engineering' AND decision = 'N';
SELECT sid, 'Matatini', 'Engineering', 'Y' FROM apply WHERE major = 'Engineering' AND decision = 'N';
INSERT INTO apply SELECT sid, 'Matatini', 'Engineering', 'Y' FROM apply WHERE major = 'Engineering' AND decision = 'N';

SELECT sid, count(distinct major) From apply Group by sid Having count(distinct major) > 2;
DELETE FROM student WHERE sid IN (SELECT sid FROM apply GROUP BY sid HAVING count(distinct major) > 2);
DELETE from apply where sid in (SELECT sid From apply Group by sid Having count(distinct major) > 2);

SELECT * FROM apply WHERE itpname = 'Matatini' and sid in (select sid from student where gpa < 3.6);
UPDATE	apply Set decision = 'Y', major = 'Economics' WHERE itpname = 'Matatini' and sid in (select sid from student where gpa < 3.6);



