# MongoDB

## 基本语法

### linux下启动MongoDB

```js
$ sudo service mongod start
$ mongo
```

### 与SQL的区别

| SQL         | MongoDB     | 解释                                 |
| ----------- | ----------- | ------------------------------------ |
| database    | database    | 数据库                               |
| table       | collection  | 表/集合                              |
| row         | document    | 行/文档                              |
| column      | filed       | 列/域                                |
| index       | index       | 索引                                 |
| table joins |             | 表连接。MongoDB不支持                |
| primary key | primary key | 主键，MongoDB自动将_id自动设置为主键 |

### 查看

```js
> show dbs // 查看数据库
> show collections //查看集合
> db.user.find() //查看数据
> db.user.find().pretty()//格式化查看的数据
> db.user.findOne()//查询第一条数据
> db.user.find({age:{$gt:22}})//查看年龄大于22的
```



### 创建	

```js
> use demo//创建数据库
> db.createCollection("user") || db.users.insert()//创建集合
```



### 删除

```js
> db.dropDatabase()//删除数据库
> db.user.drop()//删除集合
> db.user.remove({条件})
```



### 更新

```js
> db.user.update({name:'pirlo'},{$set:{age:21}})
```

 ### 符号

```
gt  >
lt  <
eq  =
gte >=
lte <=
```



