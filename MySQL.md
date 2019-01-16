## MySQL相关笔记



1. **存储过程**

   MySQL 存储过程和用户存在权限限制，需要通过存储过程定义中指定的definer来执行存储过程。

   参考：https://blog.csdn.net/zyz511919766/article/details/22083651

   

2. **事件**

   A.查看event是否开启: show variables like 'event_scheduler';

   B.将event事件计划开启: set global event_scheduler=1;

   

   ##### 创建事件

   ###### 格式：

   ```mysql
   CREATE
       [DEFINER = { user | CURRENT_USER }]
       EVENT
       [IF NOT EXISTS]
       event_name
       ON SCHEDULE schedule
       [ON COMPLETION [NOT] PRESERVE]
       [ENABLE | DISABLE | DISABLE ON SLAVE]
       [COMMENT 'comment']
       DO event_body;
   ```

   ###### 例子:

   ```mysql
   create event event_now
   on schedule
   at now()
   do insert into events_list values('event_now', now());
   ```

   

   ##### 查看事件

   ```mysql
   SHOW EVENTS;
   ```

   

   ##### 修改事件

   ###### 格式：

   ```MySQL
   ALTER
       [DEFINER = { user | CURRENT_USER }]
       EVENT event_name
       [ON SCHEDULE schedule]
       [ON COMPLETION [NOT] PRESERVE]
       [RENAME TO new_event_name]
       [ENABLE | DISABLE | DISABLE ON SLAVE]
       [COMMENT 'comment']
       [DO event_body]
   ```

   ###### 例子1：

   ```MySQL
   alter event test.event_minute
   on schedule
   every  30 second 
   do insert into events_list values('event_now', now());
   ```

   ###### 例子2：

   ```MySQL
   alter event test.event_minute
   rename to test.event_second;
   ```

   ###### 例子3：

   ```MySQL
   alter event test.event_second disable;
   alter event test.event_second enable;
   ```

   

   ##### 删除事件

   ###### 格式：

   ```MySQL
   DROP EVENT [IF EXISTS] event_name；
   ```

   ###### 例子：

   ```MySQL
   drop event if exists event_second;
   ```

   参考：https://blog.csdn.net/jesseyoung/article/details/35257527

   

3. **小数格式处理**

   A: format（1234.5678,2） ==> 1234.57

   B: 0 + CAST(1234.000 as char)  ==> 1234

   

4. **Like 多条件**

   A:

   ```mysql
   WHERE interests LIKE '%sports%' OR interests LIKE '%pub%';
   ```

   B:

   ```MySQL
   WHERE interests REGEXP 'sports|pub'；
   ```

   

