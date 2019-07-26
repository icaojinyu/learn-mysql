# MySQL基础

### 一、什么是表？
- MySQL是一种关系型数据库。关系型数据库最重要的概念就是表
- 表具有固定的列数和任意的行数，在数学上称为“关系”
- 表中的列：字段
- 表中的行：一条数据/一条记录

### 二、orm（对象关系映射）
- 表 => 类   => 定义存储结构
- 列 => 字段 => 定义存储哪些属性
- 行 => 对象 => 表示一条数据/一个对象

### 三、启动和连接MySQL
- 如果MySQL服务没有启动，则不能访问MySQL
- 启动MySQL服务：
    - 打开数据库连接之前，一定要保证MySQL服务已经开启了
    - 开启服务：`net start MySQL`
    - 关闭服务：`net stop MySQL`
- 连接数据库：
  - 格式：`mysql -u <user_account> -p <password> -h <host> -P <port>`
  - 如果连接的数据库服务器在本机上，并且端口是3306，则可以简写为：`mysql -u root -p`，回车后输密码就可连接
- 可视化工具：Navicat

### 四、常用的命令  
- 查看数据库服务器存在哪些数据库：`show databases;`
- 使用指定的数据库：`use <database_name>;`
- 查看指定的数据库中有哪些数据表：`show tables;`
- 创建指定名称的数据库：`create database <database_name>;`
- 删除数据库：`drop database <database_name>;`

### 五、存储引擎
- MyISAM：拥有较高的插入、查询速度，但不支持事务，不支持外键
- InnoDB：支持事务，支持外键，支持行级锁定，性能较低
    - InnoDB存储引擎提供了具有提交、回滚和崩溃恢复能力的事务安全。但对比MyISAM，处理效率差，且会占用更多的磁盘空间已保留数据和索引。