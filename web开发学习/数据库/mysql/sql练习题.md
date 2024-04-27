## 知识点
### distinct
select {distinct} {A} as {B} from {C}
distinct关键字是选取独立的a选项从c中并重新命名成b选项

### char_length
select tweet_id
from  Tweets
where char_length(content)>15

### left join 和on 
表示了左连接和判断条件
```
select   EmployeeUNI.unique_id,Employees.name
from Employees
left join
EmployeeUNI
on
Employees.id = EmployeeUNI.id
```

### left join ，right join , join
左连接，以选中的表为基，匹配右表
右连接，以后面的表为基，匹配左表
内连接，只是连接两个表达交集

### group by
聚合函数可以通过该选项进行分类，筛选分组数据

### having
**与 WHERE 的区别**：`WHERE` 子句用于筛选原始数据行，而 `HAVING` 子句用于筛选**分组数据**。因此，`WHERE` 在 `GROUP BY` 之前应用，而 `HAVING` 在 `GROUP BY` 之后应用

### datediff的一些计算时间差的函数
```
ADDDATE: ADDDATE(date, INTERVAL value addunit) 
#ADDDATE('yyyyMMdd',INTERVAL 1 day)

DATEDIFF: DATEDIFF(date1, date2) #date1-date2

TIMESTAMPDIFF: TIMESTAMPDIFF(DAY,'2023-01-01', '2022-12-21')
DATE_SUB: DATE_SUB('2023-12-29',INTERVAL 2 DAY) #2023-12-27
DATE_ADD: 同上
```

### cross join交叉联结
放一张图就知道是如何交叉联结了
![[Pasted image 20231021110028.png]]通过交叉联结可以比较同一个选项的迭代，差值，求和关系

### where用来筛选符合条件的选项

### group by 后面的选项
后面跟着一个选项的意思是只按照当前条件来进行分类，如果后面跟着两个参数可以按照两个选项的组合来进行
分类。

mysql中每一个派生表都需要有自己的别名

## 习题
[学生们参加测验的次数](https://leetcode.cn/problems/students-and-examinations/?envType=study-plan-v2&envId=sql-free-50)
使用交叉联结，最适合于这种每个选项在不同条件下的不同次数