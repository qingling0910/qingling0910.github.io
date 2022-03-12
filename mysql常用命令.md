mysql常用语法

1、查看当前打开的数据库
SELECT DATABASE();

2、查看数据库编码
SHOW CREATE DATABASE db_name/** db_name为要修改的数据库名 */

3、查看所有数据库
show databases;

4、查看所有数据表
show tables

5、查看指定数据看下的表
show tables from db_name;    //db_name数据库名

6、创建数据库
create database [if not exists] db_name character set = charset_name;   //[]中的内容为可选值，db_name为数据库名，charset_name为编码名如：utf8

7、修改数据库的编码
alter database db_name character set [=] charset_name;   //db_name为要修改的数据库名，charset_name为编码名

8、删除数据库
drop database [if not exists] db_name;   //db_name为要删除的数据库名，[]中的内容为可选值

9、创建数据表
create table [if not exists] tb_name (colume_name data_type PRIMARY KEY AUTO INCREMENT  
colume_name data_type,…
//colume_name为字段名 
//data_type为字段的数据类型
//PRIMARY KEY意为设置当前字段为主键
//AUTO_INCREMENT意为设置当前字段为自增长);


10、查看数据表的结构
1)show columes from tb_name;  
2)desc tb_name

11、删除数据表
drop table table_name;

12、给数据表插入数据
insert [into] tb_name [(colume_name, ….)] values (values1,values2, …)    //如果省略掉列名所有字段必须赋值，自增长字段可以赋default或null

13、查询数据
select expr,…from tb_name [where];   //expr 为表达式：*、字段名等

14、如果你想限定字段中的值为唯一的可以给字段设置唯一约束，在字段后面添加如下SQL语句
unique key

15、显示索引
show indexes from

16、修改mysql的数据表
1）如果想在一个已经建好的表中添加一列，可以用以下代码：

alter table 表名 add column 列名 varchar(20) not null;

这条语句会向已有的表中加入一列，这一列在表的最后一列位置。

2）如果我们希望添加在指定的一列，可以用：

alter table 表名 add column 列名 varchar(20) not null after user1;

注意，上面这个命令的意思是说添加addr列到user1这一列后面。

3）如果想添加到第一列的话，可以用：

alter table 表名 add column 列名 varchar(20) not null first;


40将表中，列名def改为unit

alter table table_name change  def unit char;


50将表中，列名def的列删除

alter table table_name drop column def ;

17.删除数据
delete from 表名 where 条件;


18.修改数据
update 表名 set numberid=2 where 条件


19.降序排列
select *(或具体column_name) from 表名 order by id desc;


20、添加别名
select id(列名) '别名' ,(列名) as '别名' from 表名;
