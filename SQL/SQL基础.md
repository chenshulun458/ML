1,

SELECT DISTINCT prod_id,prod_price,prod_name

FROM products

ORDER BY prod_price DESC,prod_name; 默认升序,DESC只应用到前一列

LIMIT 1 



2, 

AND 比 OR 先执行，需要括号      （）> AND >OR      IN NOT

**1、空值与空字符串不同，判断方法也不同**

- 判断NULL用is null 或者 is not null。

- 判断空字符串，要用 =”或者 <>”。

  

3,

LIMIT OFFSET从第几行开始取



4,

通配符：   LIKE 'jet%' 接受jet之后的任意字符   %x%表示匹配包含的任何  _匹配一个字符



5,

正则表达式 :     REGEXP '.' 匹配任意一个字符     (+BINARY区分大小写) (| 或) （[123] = 1|2|3）

转义 \\\前缀

P58 √



6，

mysql修改表名，列名，列类型，添加表列，删除表列 

alter table test rename test1; --修改表名 

alter table test add column name varchar(10); --添加表列 

alter table test drop column name; --删除表列 

alter table test modify address char(10) --修改表列类型 
|alter table test change address address char(40) 

alter table test change column address address1 varchar(30)



**7 join**

<img src="C:\Users\Administrator\Desktop\自学素材\2767807589-5c122586a23c4_fix732.png" style="zoom: 67%;" />



**8 GROUP BY:**

在示例3中提到group by语句中select指定的字段必须是“分组依据字段”，其他字段若想出现在select中则必须包含在聚合函数中，常见的聚合函数如下表：

| 函数        | 作用         | 支持性               |
| :---------- | :----------- | :------------------- |
| sum(列名)   | 求和         |                      |
| max(列名)   | 最大值       |                      |
| min(列名)   | 最小值       |                      |
| avg(列名)   | 平均值       |                      |
| first(列名) | 第一条记录   | 仅Access支持         |
| last(列名)  | 最后一条记录 | 仅Access支持         |
| count(列名) | 统计记录数   | 注意和count(*)的区别 |



**9 DATEDIFF**  



**10 自连接**

删除 `Person` 表中所有重复的电子邮箱

DELETE p1 FROM Person p1,

  Person p2

WHERE

  p1.Email = p2.Email AND p1.Id > p2.Id



**11 where and having**

1.where和having的区别
2.聚合函数和group by
3.where 和having的执行顺序
4.where不能使用聚合函数、having中可以使用聚合函数
1.where和having的区别
where:
where是一个约束声明,使用where来约束来自数据库的数据;
where是在结果返回之前起作用的;
where中不能使用聚合函数。
having:
having是一个过滤声明;
在查询返回结果集以后，对查询结果进行的过滤操作;
在having中可以使用聚合函数。 
2.聚合函数和group by
聚合函数就是例如SUM, COUNT, MAX, AVG等对一组(多条)数据操作的函数，需要配合group by 来使用。
\#如：
SELECT SUM(population),region FROM T01_Beijing GROUP BY region; //计算北京每个分区的人数
3.where和having的执行顺序
where 早于 group by 早于 having
where子句在聚合前先筛选记录，也就是说作用在group by 子句和having子句前，而 having子句在聚合后对组记录进行筛选
4.where不能使用聚合函数、having中可以使用聚合函数
\#筛选出北京西城、东城、海淀及各区学校数量
SELECT region,count(school)
FROM T02_Bejing_school
WHERE region IN ('海淀' , '西城' , '东城') GROUP BY region；
\#筛选出北京西城、东城、海淀三个区中学校数量超过10所的区及各区学校数量。
SELECT region,count(school)
FROM T02_Bejing_school
WHERE region IN ('海淀' , '西城' , '东城')
GROUP BY region HAVING count(school) > 10;
注意！我们不能用where来筛选超过学校数量超过10的区，因为表中不存在这样一条记录。而HAVING子句可以让我们筛选成组后的各组数据．



**12 WINDOW FUNCTION**

SELECT * 

FROM 

（SELECT *,

​			RANK() OVER (PARTITION BY 班级 

​										ORDER BY  分数) AS  rank   FROM TABLE ) as t1 

HAVING  



