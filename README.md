# springboot-quartz
springboot中使用quartz框架（持久化到数据库+springboot）


1.导入mvn依赖
2.在项目中添加quartz.properties文件（这样就不会走它自带的properties文件）
3.在数据库中创建quartz相关的表
  1）进入quartz的官网http://www.quartz-scheduler.org/，点击Downloads，下载后在目录\docs\dbTables下有常用数据库创建quartz表的脚本。
  2）百度去搜创建quartz表
4.自定义MyJobFactory，解决spring不能在quartz中注入bean的问题
5.创建调度器schedule


从数据库读取任务信息动态生成定时任务，和把quartz持久化到数据库是没有关系的。

前者是我们自己定义的业务表，
而后者是quartz使用自己的表来存储信息持久化到数据库后，就算服务器重启或是多个quartz节点也没关系，因为他们共享数据库中的任务信息。
