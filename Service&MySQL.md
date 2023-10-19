Source for Mysql:

        wget https://dev.mysql.com/get/mysql-apt-config_0.8.24-1_all.deb
        sudo apt install ./mysql-apt-config_0.8.24-1_all.deb
        rm mysql-apt-config_0.8.24-1_all.deb
Install MySql

        sudo apt update
        sudo apt install mysql-server
Connect to mysql / root is username

        mysql -u root -p
        sudo mysql
For Access

        GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' IDENTIFIED BY '12' WITH GRANT OPTION;
Check Status

        sudo systemctl status mysql
Set PassWord

        sudo mysql_secure_installation
        mysql -h 127.0.0.1 -P 3306 -u root
Stop Mysql Service

        sudo /etc/init.d/mysql stop 
Start mysql without password

        sudo mysqld_safe --skip-grant-tables & 
Restart

        sudo /etc/init.d/mysql restart
        sudo /etc/init.d/mysql start
Progress

        ps aux |grep mysql
Pill Progress

        killall mysqld mysqld_safe
Sudo

        sudo service mysql status
        sudo service mysql stop
        sudo service mysql start
        sudo start mysql
        sudo stop mysql
        sudo restart mysql
        sudo service mysql restart
# DOS DB

        Maria[]> show databases；
        Maria[]> create database jal；
        Maria[]> use jal；
                Maria[jal]> 
        Maria[jal]> show tables；
        Maria[jal]> delete from JAL_asininfo; (Query OK, 170 rows affected (0.008 sec))
        Maria[jal]> drop table JAL_asininfo;

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


# about port(Error: That port is already in use.)
check: netstat -ntlp
ready: kill -9 PID
action: kill -9 pid_number

# Log output is incomplete or unavailable
journalctl --vacuum-size=1G

# Django DB
迁移数据
        python37 manage.py makemigrations
        python37 manage.py migrate
终极办法
        1）清空app > migrations 下面除_init_.py以外的数据文件
        2）清空MySQL数据，甚至数据表，更甚至app数据库
        3）清空models.py中的创建数据表的代码
        4）执行：python37 manage.py makemigrations
        5）仅恢复models.py中的创建数据表的代码
        6）执行：python37 manage.py makemigrations

# RunServer
nohup python3 manage.py runserver 140.82.22.68:8000 &

# Server
ssh root@ip66.42.107.185 45.76.74.94
5u+GY]gaeus*k#z,
Da@3_d}CjduNUN7H
8{dT%R#mXK=*r$mC
