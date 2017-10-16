# SQL Basics and Beyond

Here we go through some basic SQL Queries and move on to not so basic stuff


## Basics

Say we have a table of Employees as below

empno|fullname|age|profession
-----|--------|---|----------
1|first employee|26|Data Consultant
2|second employee|32|Department Manager
3|third employee|24|Developer
4|fourth employee|50|CEO



### Filters
Following query will get a particular row with a simple where clause

```sql

  select * from employees where empno = "1";

```



Say we have another table for Employee Attendance as follows

empno|intime|outtime|nettime
-----|--------|---|----------
1|16-oct-2017 08:00:00|16-oct-2017 16:00:00|8
1|17-oct-2017 08:30:00|16-oct-2017 16:00:00|7.5
1|18-oct-2017 07:00:00|16-oct-2017 16:00:00|9
1|19-oct-2017 08:00:00|16-oct-2017 15:00:00|7
2|16-oct-2017 08:00:00|16-oct-2017 16:00:00|8
3|16-oct-2017 08:00:00|16-oct-2017 16:00:00|8
3|16-oct-2017 08:00:00|16-oct-2017 16:00:00|8


### Joins
Then in order to get basic attendance report with empoyee full name, the query would be made using a [Join](https://en.wikipedia.org/wiki/Join_(SQL)) Clause

```sql

  select a.fullname, b.intime, b.outtime, b.nettime
  from employees a 
  inner join b on a.empno = b.empno 
  where empno = "1";

```

fullname|intime|outtime|nettime
-----|--------|---|------------
first name|16-oct-2017 08:00:00|16-oct-2017 16:00:00|8
first name|17-oct-2017 08:30:00|16-oct-2017 16:00:00|7.5
first name|18-oct-2017 07:00:00|16-oct-2017 16:00:00|9
first name|19-oct-2017 08:00:00|16-oct-2017 15:00:00|7


### Sort
We can get the result sorted using [Order by](https://en.wikipedia.org/wiki/Order_by) clause on nettime as an example

```sql

  select a.fullname, b.intime, b.outtime, b.nettime
  from employees a 
  inner join b on a.empno = b.empno 
  where empno = "1"
  order by b.nettime desc;

```
Note that the desc clause will sort the resultset in Descending order (Default is Ascending)



More to come after this...
