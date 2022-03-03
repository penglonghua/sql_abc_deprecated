
临时记录， 肯定有一些是有问题的.
# 关于唯一约束

显示有哪些 索引

```sql
SHOW INDEX FROM userdirctory; 


添加索引
ALTER TABLE cloud.`userdirctory` add UNIQUE( `name`, `parent_id`, `stariveruserid`);

删除某个索引
ALTER TABLE userdirctory DROP INDEX `name`;
```


## 关于时间

数据库里存放的是 UNIXTIME 秒数, 可以把 秒数整成 友好时间显示.
```sql
SELECT *, FROM_UNIXTIME(ptime,'%Y-%m-%d %h:%i:%s') as `date` FROM cloud.userfile   where stariveruserid ='3414868971001219072'
   order by id desc;
```