# Listing Img - 1500 & 1500
## 主图 @1
        1500 @ 1500
        白色背景主图
## 场景 @3
        1500 @ 1500
## 标签 @3
        1500 @ 1500
        产品特性、产品特性、尺寸
## 视频 @1
        1500 @ 1500
        15秒

# A+ Img
## 大场景 @1
        970 @ 600
## 小场景 @3
        300 @ 300
## 大场景 @1
        970 @ 600
## 细节图 @3
        300 @ 300
## 大场景 @1
        970 @ 600
        礼物、送礼
## Brand Stories @1
        970 @ 600

# Fonts
        Baloo Da 2
        Eras Bold ITC
        Verdana
        Arvo

# MySql
        # Install MySql
                1) wget https://dev.mysql.com/get/mysql-apt-config_0.8.24-1_all.deb
                2) sudo apt install ./mysql-apt-config_0.8.24-1_all.deb
                3) sudo apt update
                4) sudo apt install mysql-server (pass password set)
                5) sudo systemctl status mysql (check status)
                6) sudo mysql_secure_installation (set password)
                mysql -h 127.0.0.1 -P 3306 -u root

        # stop mysql service
        sudo /etc/init.d/mysql stop 
        # restart
        sudo /etc/init.d/mysql restart
        # restart
        sudo /etc/init.d/mysql start
        # start mysql without password
        sudo mysqld_safe --skip-grant-tables & 
        # progress
        ps aux |grep mysql
        # kill progress
        killall mysqld mysqld_safe
        # connect to mysql / root is username
        mysql -u root -p 
        # sss
        sudo service mysql status
        sudo service mysql stop
        sudo service mysql start
        sudo start mysql
        sudo stop mysql
        sudo restart mysql
        sudo service mysql restart

        # DOS
                DOS窗口进入数据库 mysql -uroot -p密码
                查看数据库：show databases；
                创建数据库：create database 数据库名字；
                使用某个数据库：use 数据库名字；
                查看使用数据库中的表：show tables；
                数据库初始化执行sql文件：source +sql文件路径（直接拖就行）
                删除数据库：drop database 数据库名字；
                查看表结构：desc+表名；
                查看表中数据：select * from 表名；（当在DOS界面中显示MYSQL数据库中的表的信息时，可能会出现中文乱码问题，出现是原因是因为DOS窗口默认字符集为GBK格式，如果当前MYSQL设置的默认编码格式非GBK格式，则可能会出现乱码。
                解决方法：在输出信息前，执行以下语句：
                set names gbk;）
                查询当前使用的哪个数据库：select database（）；也可直接再use一下需要的数据库；
                查询mysql的版本号：select version（）；
                结束一条语句：\c 命令
                退出mysql：exit 命令
                查看创建表的时候使用的sql语句：show create table 表名；

        # DOS Tables
        show databases;
        use jal;
        show tables;
        # DOS delete data
        delete from JAL_asininfo; (Query OK, 170 rows affected (0.008 sec))
        drop table JAL_asininfo;

        # about port(Error: That port is already in use.)
        check: netstat -ntlp
        ready: kill -9 PID
        action: kill -9 pid_number

        # Log output is incomplete or unavailable
        journalctl --vacuum-size=1G

# RunServer
        nohup python3 manage.py runserver 140.82.22.68:8000 &

# Server
        ssh root@ip66.42.107.185 45.76.74.94
        5u+GY]gaeus*k#z,
        Da@3_d}CjduNUN7H
        8{dT%R#mXK=*r$mC

# GIT
        git fetch --all
        git reset --hard origin/分支名
        git pull
        【放弃本地修改，直接覆盖】
        git reset --hard
        git pull
        
# SoftWare
        Dummy Studio
        Autodesk Fusion
        selinc
