## -MySQL 基础SQL练习-
```sql

-- ------------------------------ ----------------------------
-- 创建语句：
-- ------------------------------ ----------------------------
CREATE TABLE students
(sno VARCHAR(3) NOT NULL, 
sname VARCHAR(4) NOT NULL,
ssex VARCHAR(2) NOT NULL, 
sbirthday DATETIME,
class VARCHAR(5))

CREATE TABLE courses
(cno VARCHAR(5) NOT NULL, 
cname VARCHAR(10) NOT NULL, 
tno VARCHAR(10) NOT NULL)

CREATE TABLE scores 
(sno VARCHAR(3) NOT NULL, 
cno VARCHAR(5) NOT NULL, 
degree NUMERIC(10, 1) NOT NULL) 

CREATE TABLE teachers 
(tno VARCHAR(3) NOT NULL, 
tname VARCHAR(4) NOT NULL, tsex VARCHAR(2) NOT NULL, 
tbirthday DATETIME NOT NULL, prof VARCHAR(6), 
depart VARCHAR(10) NOT NULL)

CREATE TABLE `grade`  (
  `low` tinyint(4) NULL DEFAULT NULL,
  `upp` tinyint(4) NULL DEFAULT NULL,
  `rank` char(1) CHARACTER SET utf8 COLLATE utf8_general_ci NULL DEFAULT NULL
) ENGINE = InnoDB CHARACTER SET = utf8 COLLATE = utf8_general_ci ROW_FORMAT = Dynamic;


```
## 插入表记录
 ```sql
-- ------------------------------ ----------------------------
-- Records of Tables
-- ------------------------------ ----------------------------

INSERT INTO STUDENTS (SNO,SNAME,SSEX,SBIRTHDAY,CLASS) VALUES (108 ,'曾华' ,'男' ,'1977-09-01',95033);
INSERT INTO STUDENTS (SNO,SNAME,SSEX,SBIRTHDAY,CLASS) VALUES (105 ,'匡明' ,'男' ,'1975-10-02',95031);
INSERT INTO STUDENTS (SNO,SNAME,SSEX,SBIRTHDAY,CLASS) VALUES (107 ,'王丽' ,'女' ,'1976-01-23',95033);
INSERT INTO STUDENTS (SNO,SNAME,SSEX,SBIRTHDAY,CLASS) VALUES (101 ,'李军' ,'男' ,'1976-02-20',95033);
INSERT INTO STUDENTS (SNO,SNAME,SSEX,SBIRTHDAY,CLASS) VALUES (109 ,'王芳' ,'女' ,'1975-02-10',95031);
INSERT INTO STUDENTS (SNO,SNAME,SSEX,SBIRTHDAY,CLASS) VALUES (103 ,'陆君' ,'男' ,'1974-06-03',95031);

INSERT INTO COURSES(CNO,CNAME,TNO)VALUES ('3-105' ,'计算机导论',825);
INSERT INTO COURSES(CNO,CNAME,TNO)VALUES ('3-245' ,'操作系统' ,804);
INSERT INTO COURSES(CNO,CNAME,TNO)VALUES ('6-166' ,'数据电路' ,856);
INSERT INTO COURSES(CNO,CNAME,TNO)VALUES ('9-888' ,'高等数学' ,100);

INSERT INTO SCORES(SNO,CNO,DEGREE)VALUES (103,'3-245',86);
INSERT INTO SCORES(SNO,CNO,DEGREE)VALUES (105,'3-245',75);
INSERT INTO SCORES(SNO,CNO,DEGREE)VALUES (109,'3-245',68);
INSERT INTO SCORES(SNO,CNO,DEGREE)VALUES (103,'3-105',92);
INSERT INTO SCORES(SNO,CNO,DEGREE)VALUES (105,'3-105',88);
INSERT INTO SCORES(SNO,CNO,DEGREE)VALUES (109,'3-105',76);
INSERT INTO SCORES(SNO,CNO,DEGREE)VALUES (101,'3-105',64);
INSERT INTO SCORES(SNO,CNO,DEGREE)VALUES (107,'3-105',91);
INSERT INTO SCORES(SNO,CNO,DEGREE)VALUES (108,'3-105',78);
INSERT INTO SCORES(SNO,CNO,DEGREE)VALUES (101,'6-166',85);
INSERT INTO SCORES(SNO,CNO,DEGREE)VALUES (107,'6-106',79);
INSERT INTO SCORES(SNO,CNO,DEGREE)VALUES (108,'6-166',81);

INSERT INTO TEACHERS(TNO,TNAME,TSEX,TBIRTHDAY,PROF,DEPART) VALUES (804,'李诚','男','1958-12-02','副教授','计算机系');
INSERT INTO TEACHERS(TNO,TNAME,TSEX,TBIRTHDAY,PROF,DEPART) VALUES (856,'张旭','男','1969-03-12','讲师','电子工程系');
INSERT INTO TEACHERS(TNO,TNAME,TSEX,TBIRTHDAY,PROF,DEPART) VALUES (825,'王萍','女','1972-05-05','助教','计算机系');
INSERT INTO TEACHERS(TNO,TNAME,TSEX,TBIRTHDAY,PROF,DEPART) VALUES (831,'刘冰','女','1977-08-14','助教','电子工程系');

INSERT INTO `grade` VALUES (90, 100, 'A');
INSERT INTO `grade` VALUES (80, 89, 'B');
INSERT INTO `grade` VALUES (70, 79, 'C');
INSERT INTO `grade` VALUES (60, 69, 'D');
INSERT INTO `grade` VALUES (0, 59, 'E');
 ```
 ## 题目问题汇总如下
 ```sql
 1、 查询Student表中的所有记录的Sname、Ssex和Class列。
2、 查询教师所有的单位即不重复的Depart列。
3、 查询Student表的所有记录。
4、 查询Score表中成绩在60到80之间的所有记录。
5、 查询Score表中成绩为85，86或88的记录。
6、 查询Student表中“95031”班或性别为“女”的同学记录。
7、 以Class降序查询Student表的所有记录。
8、 以Cno升序、Degree降序查询Score表的所有记录。
9、 查询“95031”班的学生人数。
10、查询Score表中的最高分的学生学号和课程号。
11、查询‘3-105’号课程的平均分。
12、查询Score表中至少有5名学生选修的并以3开头的课程的平均分数。
13、查询最低分大于70，最高分小于90的Sno列。
14、查询所有学生的Sname、Cno和Degree列。
15、查询所有学生的Sno、Cname和Degree列。
16、查询所有学生的Sname、Cname和Degree列。
17、查询“95033”班所选课程的平均分。
18、假设使用如下命令建立了一个grade表：
create table grade(low   number(3,0),upp   number(3),rank   char(1));
insert into grade values(90,100,’A’);
insert into grade values(80,89,’B’);
insert into grade values(70,79,’C’);
insert into grade values(60,69,’D’);
insert into grade values(0,59,’E’);
commit;
现查询所有同学的Sno、Cno和rank列。
19、查询选修“3-105”课程的成绩高于“109”号同学成绩的所有同学的记录。
20、查询score中选学一门以上课程的同学中分数为非最高分成绩的记录。
21、查询成绩高于学号为“109”、课程号为“3-105”的成绩的所有记录。
22、查询和学号为108的同学同年出生的所有学生的Sno、Sname和Sbirthday列。
23、查询“张旭“教师任课的学生成绩。
24、查询选修某课程的同学人数多于5人的教师姓名。
25、查询95033班和95031班全体学生的记录。
26、查询存在有85分以上成绩的课程Cno.
27、查询出“计算机系“教师所教课程的成绩表。
28、查询“计算机系”与“电子工程系“不同职称的教师的Tname和Prof。
29、查询选修编号为“3-105“课程且成绩至少高于选修编号为“3-245”的同学的Cno、Sno和Degree,并按Degree从高到低次序排序。
30、查询选修编号为“3-105”且成绩高于选修编号为“3-245”课程的同学的Cno、Sno和Degree.
31、查询所有教师和同学的name、sex和birthday.
32、查询所有“女”教师和“女”同学的name、sex和birthday.
33、查询成绩比该课程平均成绩低的同学的成绩表。
34、查询所有任课教师的Tname和Depart.
35  查询所有未讲课的教师的Tname和Depart. 
36、查询至少有2名男生的班号。
37、查询Student表中不姓“王”的同学记录。
38、查询Student表中每个学生的姓名和年龄。
39、查询Student表中最大和最小的Sbirthday日期值。
40、以班号和年龄从大到小的顺序查询Student表中的全部记录。
41、查询“男”教师及其所上的课程。
42、查询最高分同学的Sno、Cno和Degree列。
43、查询和“李军”同性别的所有同学的Sname.
44、查询和“李军”同性别并同班的同学Sname.
45、查询所有选修“计算机导论”课程的“男”同学的成绩表

 ```sql
 1、 查询Student表中的所有记录的Sname、Ssex和Class列。
2、 查询教师所有的单位即不重复的Depart列。
3、 查询Student表的所有记录。
4、 查询Score表中成绩在60到80之间的所有记录。
5、 查询Score表中成绩为85，86或88的记录。
6、 查询Student表中“95031”班或性别为“女”的同学记录。
7、 以Class降序查询Student表的所有记录。
8、 以Cno升序、Degree降序查询Score表的所有记录。
9、 查询“95031”班的学生人数。
10、查询Score表中的最高分的学生学号和课程号。
11、查询‘3-105’号课程的平均分。
12、查询Score表中至少有5名学生选修的并以3开头的课程的平均分数。
13、查询最低分大于70，最高分小于90的Sno列。
14、查询所有学生的Sname、Cno和Degree列。
15、查询所有学生的Sno、Cname和Degree列。
16、查询所有学生的Sname、Cname和Degree列。
17、查询“95033”班所选课程的平均分。
18、针对grade表,现查询所有同学的Sno、Cno和rank列。
19、查询选修“3-105”课程的成绩高于“109”号同学成绩的所有同学的记录。
20、查询score中选学一门以上课程的同学中分数为非最高分成绩的记录。
21、查询成绩高于学号为“109”、课程号为“3-105”的成绩的所有记录。
22、查询和学号为108的同学同年出生的所有学生的Sno、Sname和Sbirthday列。
23、查询“张旭“教师任课的学生成绩。
24、查询选修某课程的同学人数多于5人的教师姓名。
25、查询95033班和95031班全体学生的记录。
26、查询存在有85分以上成绩的课程Cno.
27、查询出“计算机系“教师所教课程的成绩表。
28、查询“计算机系”与“电子工程系“不同职称的教师的Tname和Prof。
29、查询选修编号为“3-105“课程且成绩至少高于选修编号为“3-245”的同学的Cno、Sno和Degree,并按Degree从高到低次序排序。
30、查询选修编号为“3-105”且成绩高于选修编号为“3-245”课程的同学的Cno、Sno和Degree.
31、查询所有教师和同学的name、sex和birthday.
32、查询所有“女”教师和“女”同学的name、sex和birthday.
33、查询成绩比该课程平均成绩低的同学的成绩表。
34、查询所有任课教师的Tname和Depart.
35  查询所有未讲课的教师的Tname和Depart. 
36、查询至少有2名男生的班号。
37、查询Student表中不姓“王”的同学记录。
38、查询Student表中每个学生的姓名和年龄。
39、查询Student表中最大和最小的Sbirthday日期值。
40、以班号和年龄从大到小的顺序查询Student表中的全部记录。
41、查询“男”教师及其所上的课程。
42、查询最高分同学的Sno、Cno和Degree列。
43、查询和“李军”同性别的所有同学的Sname.
44、查询和“李军”同性别并同班的同学Sname.
45、查询所有选修“计算机导论”课程的“男”同学的成绩表

 ```
 ## 相关题目解答（自己的思路，有问题可列出issues）
 ```sql 
-- 1、 查询students表中的所有记录的Sname、Ssex和Class列。
 SELECT Sname,Ssex, Class from students;
-- 2、 查询教师所有的单位即不重复的Depart列。
 select distinct depart from teachers ;
-- 3、 查询students表的所有记录。
select * from students;  
-- 4、 查询Score表中成绩在60到80之间的所有记录。
select * from scores  as  a where a.degree between 60 and 80 ;
-- 5、 查询Score表中成绩为85，86或88的记录。
select * from scores as a where a.degree in (85,86,88);
-- 6、 查询students表中“95031”班或性别为“女”的同学记录。
select * from students as a where a.class='95031' or a.ssex='女';
-- 7、 以Class降序查询students表的所有记录。
select * from students order by class desc;
-- 8、 以Cno升序、Degree降序查询Score表的所有记录。
select * from scores as a order by a.cno asc,a.degree desc;
-- 9、 查询“95031”班的学生人数。
select count(1) from students where class='95031';
-- 10、【***】查询Score表中的最高分的学生学号和课程号。
select sno,cno from scores 
  where degree = (select max(s.degree) from scores as s );-- [自己写的]
select sno,cno from scores order by degree desc limit 1; -- [博客推荐的]感觉不是很对 ，如果有多个最高分呢？！
-- 11、查询‘3-105’号课程的平均分。
select avg(degree) from scores where cno='3-105';
-- 12、查询Score表中至少有5名学生选修的并以3开头的课程的平均分数。
select cno,avg(degree) from scores where cno like '3%' group by cno having count(sno) >= 5 ;
-- 13、【***】查询最低分大于70，最高分小于90的Sno列。
select sno from scores group by sno having MIN(degree) > 70 and MAX(degree) < 90;
-- 14、查询所有学生的Sname、Cno和Degree列。
select stu.sname,sc.cno,sc.degree from students stu left join scores sc on stu.sno=sc.sno;
-- 15、查询所有学生的Sno、Cname和Degree列。
select stu.sno,cs.cname,sc.degree from students as stu        
      left join scores as sc on stu.sno=sc.sno 
      left join courses as cs on sc.cno=cs.cno
      ;
-- 16、查询所有学生的Sname、Cname和Degree列。
select stu.sname,cs.cname,sc.degree from students as stu 
     left join scores as sc on sc.sno=stu.sno
     left join courses as cs on cs.cno=sc.cno
     ;
-- 17、【***】查询“95033”班所选课程的平均分。
select cs.cname,cs.cno,avg(sc.degree) from students as stu 
  left join scores as sc on sc.sno=stu.sno 
  left join courses as cs on cs.cno=sc.cno
  where stu.class='95033' 
  group by cs.cno,cs.cname having cs.cname is not null
  ;
  

-- 18、【***】假设使用如下命令建立了一个grade表：
-- CREATE TABLE grade(low TINYINT,upp TINYINT,rank CHAR(1));
-- INSERT INTO grade VALUES(90,100,'A');
-- INSERT INTO grade VALUES(80,89,'B');
-- INSERT INTO grade VALUES(70,79,'C');
-- INSERT INTO grade VALUES(60,69,'D');
-- INSERT INTO grade VALUES(0,59,'E');
-- 现查询所有同学的Sno、Cno和rank列。
select sc.sno,sc.cno,g.rank from scores as sc left join grade as g on (sc.degree >= g.low and sc.degree <= g.upp) order by sc.sno
 ;
-- 19、【****】查询选修“3-105”课程的成绩高于“109”号同学成绩的所有同学的记录。
-- 理解为了相应同学表信息
select st.* from students as st left join scores as sc  on sc.sno=st.sno
  where sc.cno = '3-105' 
   and sc.degree >  (select degree from scores where sno='109' and cno='3-105')
;
-- 这个比较好
SELECT s1.Sno,s1.Degree
FROM Scores AS s1 INNER JOIN Scores AS s2
ON(s1.Cno=s2.Cno AND s1.Degree>s2.Degree)
WHERE s1.Cno='3-105' AND s2.Sno='109'
ORDER BY s1.Sno;


-- 20、【****】查询score中选学一门以上课程的同学中分数为非最高分成绩的记录。

select s.* from scores as s 
 left join (select sno from scores as sc group by sno having count(cno) > 1 ) as ss on ss.sno=s.sno 
 where s.degree 
  not in (select max(degree) from scores as sc -- 找选择一门课以上的那些人的每个课程的最大分数
       inner join  (select sno from scores as sc group by sno having count(cno) > 1 ) 
       as snot  on snot.sno=sc.sno
       group by cno 
      )
;
-- SELECT sno
-- FROM scores
-- GROUP BY sno
-- HAVING COUNT(cno) > 1 AND degree != MAX(degree)
-- ;

-- 21、查询成绩高于学号为“109”、课程号为“3-105”的成绩的所有记录。
select sc1.* from scores as sc1 inner join scores as sc2 on sc1.degree > sc2.degree 
where sc2.sno='109' and sc2.cno='3-105'
;
-- 22、查询和学号为108的同学同年出生的所有学生的Sno、Sname和Sbirthday列。
select s1.sno,s1.sname,s2.sbirthday  from students as s1 inner join students as s2 on left(s1.sbirthday,4)=left(s2.sbirthday ,4)
where s2.sno='105'  and s1.sno != s2.sno;
-- select left('12345678',4)
-- select right('12345678',4)
-- select substring('12345678',2,3)
-- select substring_index('12345678','8',1)

-- 23、查询“张旭“教师任课的学生成绩。
select sc.* from scores as sc 
 left join courses as cs on cs.cno=sc.cno
 left join teachers as t on t.tno=cs.tno
where t.tname='张旭'
-- 24、查询选修某课程的同学人数多于5人的教师姓名。
select t.tname from teachers as t 
inner join (select c.tno,count(s.sno) as snoC from scores as s inner join courses as c on c.cno=s.cno group by s.cno having snoC > 5) as ss
on ss.tno=t.tno
 ;
 -- 示例
 SELECT DISTINCT Tname
 FROM Scores as s
 INNER JOIN Courses as c ON(s.Cno=c.Cno) 
 INNER JOIN Teachers as t ON(c.Tno=t.Tno)
WHERE c.Cno IN(SELECT Cno FROM Scores GROUP BY(Cno) HAVING COUNT(Sno)>5);

-- 25、查询95033班和95031班全体学生的记录。
select * from students where class in (95033,95031);
-- 26、查询存在有85分以上成绩的课程Cno.
select distinct cno from scores where degree > 85;
-- 27、查询出“计算机系“教师所教课程的成绩表。
select t.tno,t.tname,s.* from scores as s 
inner join courses as c on c.cno=s.cno 
inner join teachers as t on t.tno=c.tno and t.depart='计算机系'
;
-- 示例
SELECT Tname,Cname,SName,Degree
FROM Teachers INNER JOIN Courses
ON(Teachers.Tno=Courses.Tno) INNER JOIN Scores
ON(Courses.Cno=Scores.Cno) INNER JOIN Students
ON(Scores.Sno=Students.Sno)
WHERE Teachers.Depart='计算机系'
ORDER BY Tname,Cname,Degree DESC;
-- 28、查询“计算机系”与“电子工程系“不同职称的教师的Tname和Prof。
select *from teachers as t where t.depart='计算机系' and t.prof not in (select distinct prof from teachers where depart ='电子工程系');

-- 29、查询选修编号为“3-105“课程且成绩至少高于选修编号为“3-245”的同学的Cno、Sno和Degree,并按Degree从高到低次序排序。
 -- 合A至少高于集合B】：A最小的元素不小于B中元素
SELECT Cno,Sno,Degree
FROM Scores
WHERE Cno='3-105' AND Degree > ANY(
    SELECT Degree
    FROM Scores
    WHERE Cno='3-245')
ORDER BY Degree DESC;

SELECT * FROM Scores WHERE Cno='3-245';
SELECT * FROM Scores WHERE Cno='3-105';

-- 30、查询选修编号为“3-105”且成绩高于选修编号为“3-245”课程的同学的Cno、Sno和Degree. 
 select cno,sno,degree from scores where cno='3-105' and degree > ALL( select degree from scores where cno='3-245')
 ;

-- 31、查询所有教师和同学的name、sex和birthday.
   select t.tname as name ,t.tsex as sex ,t.tbirthday as birthday from  teachers as t
   union  
   select s.sname as name ,s.ssex as sex ,s.sbirthday as birthday from students as s
   ;
-- 32、查询所有“女”教师和“女”同学的name、sex和birthday.
   select tname name ,tsex sex,tbirthday birthday  from teachers where tsex='女'
    union
    select sname name , ssex sex ,sbirthday birthday from students where ssex ='女'
 ;
-- 33、查询成绩比该课程平均成绩低的同学的成绩表。
  select s.* from scores as s inner join  (select cno,avg(degree) as degree from scores group by cno ) as gg on gg.cno=s.cno and s.degree < gg.degree;
 
-- 34、查询所有[任课]教师的Tname和Depart.
   select tname,depart  from teachers t left join courses as c on t.tno=c.tno
   ;
   
-- 35  查询所有未讲课的教师的Tname和Depart. 
select tname,depart  from teachers t left join courses as c on t.tno=c.tno 
where c.tno is NULL
   ;    
 -- 等价于
   SELECT Tname,Depart FROM Teachers WHERE Tno NOT IN( SELECT Tno FROM Courses);

-- 36、查询至少有2名男生的班号。
   select class,count(if(ssex='男',1,NULL)) sexC from students group by class having sexC >= 2;
   
-- 37、查询students表中不姓“王”的同学记录。
  select * from students where sname not like '王%';
-- 38、查询students表中每个学生的姓名和年龄。
  select sname,TIMESTAMPDIFF(YEAR,sbirthday,CURDATE()) as age  from students ;
--    select TIMESTAMPDIFF(YEAR,'1994-07-26',CURDATE())
-- 39、查询students表中最大和最小的Sbirthday日期值。
   SELECT MIN(Sbirthday),MAX(Sbirthday) FROM Students;
-- 40、以班号和年龄从大到小的顺序查询students表中的全部记录。
   select *from students order by class desc ,sbirthday desc 
-- 41、查询“男”教师及其所上的课程。
  SELECT Teachers.Tname,Courses.Cname FROM Teachers INNER JOIN Courses ON(Teachers.Tno=Courses.Tno)WHERE Teachers.Tsex='男';
-- 42、查询最高分同学的Sno、Cno和Degree列。
  select * from scores group by sno having degree = MAX(degree)
  ;
-- 43、查询和“李军”同性别的所有同学的Sname.
  select * from students where sname != '李军' and ssex =
  (select ssex from students where sname='李军' limit 1 )
  ;
  -- 等同于
  select a.* from students as a inner join students as b on a.ssex=b.ssex
  where b.sname='李军' and a.sname!='李军'
  ;
-- 44、查询和“李军”同性别并同班的同学Sname.
select a.* from students as a inner join students as b on a.ssex=b.ssex and a.class=b.class
  where b.sname='李军' and a.sname!='李军' ;
-- 45、查询所有选修“计算机导论”课程的“男”同学的成绩表
    select s.* from scores s 
  inner join students as st on st.sno=s.sno 
  inner join courses c on c.cno=s.cno
  where c.cname='计算机导论' and st.ssex='男'
```
