本文主要记录ubuntu24.04安装postgres16和ubuntu22.04安装postgres15
# 一、ubuntu24安装postgres16
- 1、sudo aptupdate
- 2、安装数据库服务端和客户端
  sudo apt install postgres-16
- 3、验证PostgreSql服务是否启动
  $ sudo systemctl status psotgresql
- 4、查看版本
  $ psql --version
- 5、更改密码
  sudo -u postgres psql
  进入数据库后
  postgres=# alter user postgres pssword '';


- 6、基本配置（远程访问链接）
  sudo vim /etc/postgresql/16/main/postgresql.conf
  取消listen_addresses开头的注释，用*替换localhost
  接下来，编辑sudo vim /etc/postgresql/16/main/pg_hba.conf
  host all all 0.0.0.0/0 trust

  基本命令：
  接入PostgreSQL数据库: psql -h IP地址 -p 端口 -U 数据库名

  之后会要求输入数据库密码
  
   
  
  二、访问数据库
  
  1、列举数据库：\l
  2、选择数据库：\c 数据库名
  3、查看该某个库中的所有表：\dt
  4、切换数据库：\c interface
  5、查看某个库中的某个表结构：\d 表名
  6、查看某个库中某个表的记录：select * from apps limit 1;
  7、显示字符集：\encoding
  8、退出psgl：\q
