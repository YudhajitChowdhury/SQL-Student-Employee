# SQL-Student-Employee
SQL Student-Employee List Assignment 1 (28.01.2020)
#
#

SQL*Plus: Release 11.2.0.2.0 Production on Sun Feb 2 20:39:24 2020

Copyright (c) 1982, 2014, Oracle.  All rights reserved.

SQL> connect 
ERROR:
ORA-01017: invalid username/password; logon denied


SQL> connect 
Connected.
SQL> create table student (id number, name varchar2(20) , stream varchar2(10));

Table created.

SQL> insert into student (1, 'Kennedy', 'CSE');
insert into student (1, 'Kennedy', 'CSE')
                     *
ERROR at line 1:
ORA-00928: missing SELECT keyword


SQL> insert into student values (1, 'Kennedy', 'CSE');

1 row created.

SQL> insert into student values (2, 'Johnson', 'IT');

1 row created.

SQL> insert into student values (3, 'Nixon', 'CSE');

1 row created.

SQL> insert into student values (4, 'Ford', 'ECE');

1 row created.

SQL> insert into student values (5, 'Carter', 'ECE');

1 row created.

SQL> insert into student values (6, 'Reagan', 'CSE');

1 row created.

SQL> insert into student values (7, 'Bush', 'IT');

1 row created.

SQL> insert into student values (8, 'Clinton', 'IT');

1 row created.

SQL> insert into student values (9, 'Obama', 'ECE');

1 row created.

SQL> insert into student values (10, 'Trump', 'CSE');

1 row created.

SQL> alter table student rename column id to roll;

Table altered.

SQL> ALTER table student add address varchar2(20) default 'kolkata';

Table altered.

SQL> ALTER table student address varchar2(20) default 'Kolkata';
ALTER table student address varchar2(20) default 'Kolkata'
                    *
ERROR at line 1:
ORA-01735: invalid ALTER TABLE option


SQL> ALTER table student add address varchar2(20) default 'Kolkata';
ALTER table student add address varchar2(20) default 'Kolkata'
                        *
ERROR at line 1:
ORA-01430: column being added already exists in table


SQL> update student set age=21 where id=1;
update student set age=21 where id=1
                                *
ERROR at line 1:
ORA-00904: "ID": invalid identifier


SQL> update student set age=21 where roll=1;
update student set age=21 where roll=1
                   *
ERROR at line 1:
ORA-00904: "AGE": invalid identifier


SQL> ALTER TABLE Student
  2  add age number;

Table altered.

SQL> select * from student;

      ROLL NAME                 STREAM     ADDRESS                     AGE
---------- -------------------- ---------- -------------------- ----------
         1 Kennedy              CSE        kolkata
         2 Johnson              IT         kolkata
         3 Nixon                CSE        kolkata
         4 Ford                 ECE        kolkata
         5 Carter               ECE        kolkata
         6 Reagan               CSE        kolkata
         7 Bush                 IT         kolkata
         8 Clinton              IT         kolkata
         9 Obama                ECE        kolkata
        10 Trump                CSE        kolkata

10 rows selected.

SQL> update ndr set age=21 where id=1;
update ndr set age=21 where id=1
       *
ERROR at line 1:
ORA-00942: table or view does not exist


SQL> update ndr set age=21 where id=1;
update ndr set age=21 where id=1
       *
ERROR at line 1:
ORA-00942: table or view does not exist


SQL> update student set age=21 where id=1;
update student set age=21 where id=1
                                *
ERROR at line 1:
ORA-00904: "ID": invalid identifier


SQL> update student set age=21 where roll=1;

1 row updated.

SQL> update student set age=22 where roll=2;

1 row updated.

SQL> update student set age=23 where roll=3;

1 row updated.

SQL> update student set age=21 where roll=4;

1 row updated.

SQL> update student set age=25 where roll=5;

1 row updated.

SQL> update student set age=30 where roll=6;

1 row updated.

SQL> update student set age=26 where roll=7;

1 row updated.

SQL> update student set age=23 where roll=8;

1 row updated.

SQL> update student set age=29 where roll=9;

1 row updated.

SQL> update student set age=24 where roll=10;

1 row updated.

SQL> alter table student modify roll primary key;

Table altered.

SQL> select * from student;

      ROLL NAME                 STREAM     ADDRESS                     AGE
---------- -------------------- ---------- -------------------- ----------
         1 Kennedy              CSE        kolkata                      21
         2 Johnson              IT         kolkata                      22
         3 Nixon                CSE        kolkata                      23
         4 Ford                 ECE        kolkata                      21
         5 Carter               ECE        kolkata                      25
         6 Reagan               CSE        kolkata                      30
         7 Bush                 IT         kolkata                      26
         8 Clinton              IT         kolkata                      23
         9 Obama                ECE        kolkata                      29
        10 Trump                CSE        kolkata                      24

10 rows selected.

SQL> alter table student add marks number;

Table altered.

SQL> update student set marks=57 where roll=1;

1 row updated.

SQL> update student set marks=61 where roll=2;

1 row updated.

SQL> update student set marks=59 where roll=3;

1 row updated.

SQL> update student set marks=71 where roll=4;

1 row updated.

SQL> update student set marks=7 where roll=4;

1 row updated.

SQL> update student set marks=71 where roll=4;

1 row updated.

SQL> update student set marks=89 where roll=5;

1 row updated.

SQL> update student set marks=50 where roll=6;

1 row updated.

SQL> update student set marks=41 where roll=7;

1 row updated.

SQL> update student set marks=30 where roll=8;

1 row updated.

SQL> update student set marks=68 where roll=9;

1 row updated.

SQL> update student set marks=70 where roll=10;

1 row updated.

SQL> DELETE FROM student WHERE marks<50;

2 rows deleted.

SQL> update student set marks=41 where roll=7;

0 rows updated.

SQL> select * from student;

      ROLL NAME                 STREAM     ADDRESS                     AGE
---------- -------------------- ---------- -------------------- ----------
     MARKS
----------
         1 Kennedy              CSE        kolkata                      21
        57

         2 Johnson              IT         kolkata                      22
        61

         3 Nixon                CSE        kolkata                      23
        59


      ROLL NAME                 STREAM     ADDRESS                     AGE
---------- -------------------- ---------- -------------------- ----------
     MARKS
----------
         4 Ford                 ECE        kolkata                      21
        71

         5 Carter               ECE        kolkata                      25
        89

         6 Reagan               CSE        kolkata                      30
        50


      ROLL NAME                 STREAM     ADDRESS                     AGE
---------- -------------------- ---------- -------------------- ----------
     MARKS
----------
         9 Obama                ECE        kolkata                      29
        68

        10 Trump                CSE        kolkata                      24
        70


8 rows selected.

SQL> ALTER TABLE Customers
  2
SQL> alter table student drop column address;

Table altered.

SQL> select * from student;

      ROLL NAME                 STREAM            AGE      MARKS
---------- -------------------- ---------- ---------- ----------
         1 Kennedy              CSE                21         57
         2 Johnson              IT                 22         61
         3 Nixon                CSE                23         59
         4 Ford                 ECE                21         71
         5 Carter               ECE                25         89
         6 Reagan               CSE                30         50
         9 Obama                ECE                29         68
        10 Trump                CSE                24         70

8 rows selected.

SQL> SELECT * INTO employee FROM emp;
SELECT * INTO employee FROM emp
              *
ERROR at line 1:
ORA-00905: missing keyword


SQL> create table employee as select empno,ename,job,sal from emp;

Table created.

SQL> select * from employee;

     EMPNO ENAME      JOB              SAL
---------- ---------- --------- ----------
      7839 KING       PRESIDENT       5000
      7698 BLAKE      MANAGER         2850
      7782 CLARK      MANAGER         2450
      7566 JONES      MANAGER         2975
      7788 SCOTT      ANALYST         3000
      7902 FORD       ANALYST         3000
      7369 SMITH      CLERK            800
      7499 ALLEN      SALESMAN        1600
      7521 WARD       SALESMAN        1250
      7654 MARTIN     SALESMAN        1250
      7844 TURNER     SALESMAN        1500

     EMPNO ENAME      JOB              SAL
---------- ---------- --------- ----------
      7876 ADAMS      CLERK           1100
      7900 JAMES      CLERK            950
      7934 MILLER     CLERK           1300

14 rows selected.

SQL> select * from employee order by sal;

     EMPNO ENAME      JOB              SAL
---------- ---------- --------- ----------
      7369 SMITH      CLERK            800
      7900 JAMES      CLERK            950
      7876 ADAMS      CLERK           1100
      7654 MARTIN     SALESMAN        1250
      7521 WARD       SALESMAN        1250
      7934 MILLER     CLERK           1300
      7844 TURNER     SALESMAN        1500
      7499 ALLEN      SALESMAN        1600
      7782 CLARK      MANAGER         2450
      7698 BLAKE      MANAGER         2850
      7566 JONES      MANAGER         2975

     EMPNO ENAME      JOB              SAL
---------- ---------- --------- ----------
      7902 FORD       ANALYST         3000
      7788 SCOTT      ANALYST         3000
      7839 KING       PRESIDENT       5000

14 rows selected.

SQL> select distinct job from employee;

JOB
---------
CLERK
SALESMAN
PRESIDENT
MANAGER
ANALYST

SQL> select distinct ename,empno from employee;

ENAME           EMPNO
---------- ----------
BLAKE            7698
MILLER           7934
KING             7839
CLARK            7782
TURNER           7844
SCOTT            7788
FORD             7902
SMITH            7369
JAMES            7900
ALLEN            7499
WARD             7521

ENAME           EMPNO
---------- ----------
MARTIN           7654
ADAMS            7876
JONES            7566

14 rows selected.

SQL> select * from employee order by sal;

     EMPNO ENAME      JOB              SAL
---------- ---------- --------- ----------
      7369 SMITH      CLERK            800
      7900 JAMES      CLERK            950
      7876 ADAMS      CLERK           1100
      7654 MARTIN     SALESMAN        1250
      7521 WARD       SALESMAN        1250
      7934 MILLER     CLERK           1300
      7844 TURNER     SALESMAN        1500
      7499 ALLEN      SALESMAN        1600
      7782 CLARK      MANAGER         2450
      7698 BLAKE      MANAGER         2850
      7566 JONES      MANAGER         2975

     EMPNO ENAME      JOB              SAL
---------- ---------- --------- ----------
      7902 FORD       ANALYST         3000
      7788 SCOTT      ANALYST         3000
      7839 KING       PRESIDENT       5000

14 rows selected.

SQL> select * from employee where sal in( 1000,);
select * from employee where sal in( 1000,)
                                          *
ERROR at line 1:
ORA-00936: missing expression


SQL> select * from employee where sal in( 1000,5000);

     EMPNO ENAME      JOB              SAL
---------- ---------- --------- ----------
      7839 KING       PRESIDENT       5000

SQL> select * from employee where sal>=1000;

     EMPNO ENAME      JOB              SAL
---------- ---------- --------- ----------
      7839 KING       PRESIDENT       5000
      7698 BLAKE      MANAGER         2850
      7782 CLARK      MANAGER         2450
      7566 JONES      MANAGER         2975
      7788 SCOTT      ANALYST         3000
      7902 FORD       ANALYST         3000
      7499 ALLEN      SALESMAN        1600
      7521 WARD       SALESMAN        1250
      7654 MARTIN     SALESMAN        1250
      7844 TURNER     SALESMAN        1500
      7876 ADAMS      CLERK           1100

     EMPNO ENAME      JOB              SAL
---------- ---------- --------- ----------
      7934 MILLER     CLERK           1300

12 rows selected.

SQL> select * from employee where sal>=1000 and sal<=3000;

     EMPNO ENAME      JOB              SAL
---------- ---------- --------- ----------
      7698 BLAKE      MANAGER         2850
      7782 CLARK      MANAGER         2450
      7566 JONES      MANAGER         2975
      7788 SCOTT      ANALYST         3000
      7902 FORD       ANALYST         3000
      7499 ALLEN      SALESMAN        1600
      7521 WARD       SALESMAN        1250
      7654 MARTIN     SALESMAN        1250
      7844 TURNER     SALESMAN        1500
      7876 ADAMS      CLERK           1100
      7934 MILLER     CLERK           1300

11 rows selected.

SQL> select SAL,sal+1000 from employee where sal between 950 and 1250;

       SAL   SAL+1000
---------- ----------
      1250       2250
      1250       2250
      1100       2100
       950       1950

SQL> select * from employee;

     EMPNO ENAME      JOB              SAL
---------- ---------- --------- ----------
      7839 KING       PRESIDENT       5000
      7698 BLAKE      MANAGER         2850
      7782 CLARK      MANAGER         2450
      7566 JONES      MANAGER         2975
      7788 SCOTT      ANALYST         3000
      7902 FORD       ANALYST         3000
      7369 SMITH      CLERK            800
      7499 ALLEN      SALESMAN        1600
      7521 WARD       SALESMAN        1250
      7654 MARTIN     SALESMAN        1250
      7844 TURNER     SALESMAN        1500

     EMPNO ENAME      JOB              SAL
---------- ---------- --------- ----------
      7876 ADAMS      CLERK           1100
      7900 JAMES      CLERK            950
      7934 MILLER     CLERK           1300

14 rows selected.

SQL> select SAL,(sal+1000) inc from ndr where sal between 2000 and 3000;
select SAL,(sal+1000) inc from ndr where sal between 2000 and 3000
                               *
ERROR at line 1:
ORA-00942: table or view does not exist


SQL> select SAL,(sal+1000) inc from ndr where sal between 950 and 1250;
select SAL,(sal+1000) inc from ndr where sal between 950 and 1250
                               *
ERROR at line 1:
ORA-00942: table or view does not exist


SQL> select SAL,(sal+1000) inc from student where sal between 950 and 1250;
select SAL,(sal+1000) inc from student where sal between 950 and 1250
                                             *
ERROR at line 1:
ORA-00904: "SAL": invalid identifier
