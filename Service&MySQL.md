# Server Example
        Vultr
        Debian 11: LittleKris Chicago
        Debian 11: JAL_3.9kr Dallas

# Deployment service
## Connect Server
connect tools

        win:xshell***** | macos:terminal*
connect method

        ssh root@ip
Update Server Soft

        sudo apt update
        sudo apt upgrade
## Install python==3.9/3.10
## Install Django==4.2/5.0 | Flask | nodejs
        pip install Django==4.2

## Install Nodejs npm
1) update soft

        sudo apt-get update
        sudo apt-get upgrade
2) install

        sudo apt-get install nodejs npm
3) check version

        nodejs -v | npm -v
4) install React package

        npm install webpack webpack-cli --save-dev
5) pay attenion

        if some error out when 'npm run build', try '3) check version' first


## Django DB / makemigrations & migrate
- makemigrations & migrate

        python37 manage.py makemigrations | python37 manage.py makemigrations app_name
        python37 manage.py migrate
- pay attention

        if tip 1146, that is smoeone table in db does not exsit, check any *.py
        maybe models.py has been useing, it is earlier run than makemigrations / migrate.
  

## RunServer
### 2 methods could runserver
- install tmux

        sudo apt update
        sudo apt install tmux -y
- install scrren

        sudo apt update
        sudo apt install screen -y
### runserver
        tmux new -s service1
        screen -S service1
### check session
        tmux ls
        screen -ls
### into session
        tmux attach -t service1
        tmux a -t service1
        screen -r service1
### kill session
        tmux kill-session -t service1
### exit session
        tmux: 'Ctrl+B' > 'D'
        screen: 'Ctrl+A' > 'D'
### more
        tmux / screen	手动管理多个终端	        进程不会随终端关闭而停止	⭐⭐⭐⭐⭐
        nohup / &       简单临时后台运行	        终端关闭后进程依然运行	⭐⭐⭐
        systemd	        服务器长期运行，开机自启	是	                ⭐⭐⭐⭐⭐
        Docker	        容器化部署	        是	                ⭐⭐⭐⭐⭐

## About fire wall, and relax port

        iptables -I INPUT -p tcp --dport 8000 -j ACCEPT
        

## Install MySQL | mysqlclient | MariaDB
### Install 'mysqlclient' on Debian 11 with any error, try install MySQL dependency package first

        sudo apt-get install default-libmysqlclient-dev
### Install MariaDB(packages) by what???

        https://runebook.dev/zh/docs/mariadb/installing-mariadb-deb-files/index#installing-mariadb-packages-with-apt
### Install mysql-server by apt

        sudo apt install mysql-server
### Download & Install Mysql
> downloade
        
        wget https://dev.mysql.com/get/mysql-apt-config_0.8.24-1_all.deb
> install by apt
        
        sudo apt install ./mysql-apt-config_0.8.24-1_all.deb
> remove

        rm mysql-apt-config_0.8.24-1_all.deb
### Connect to DB

        mysql -u root -p | sudo mysql | mysql
### Create User

        CREATE USER 'root'@'localhost' IDENTIFIED BY 'insert_password';
### Authorize

        GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' IDENTIFIED BY 'insert_password' WITH GRANT OPTION;
### DOS DB
> on PC
        
        1) cd C:\Program Files\MySQL\MySQL Server 8.0\bin
        2) mysql -u root -p
> on Server
        
        mysql -u root -p
> enter MySql

        Maria[]> show databases；
        Maria[]> create database jal；
        Maria[]> use jal；
        Maria[jal]> 
        Maria[jal]> show tables；
        Maria[jal]> select * from JAL_account;
        Maria[jal]> delete from JAL_asininfo; (Query OK, 170 rows affected (0.008 sec))
        Maria[jal]> drop table JAL_asininfo;
        Maria[jal]> rename table meandmrleo_listing to jal_listing;
### Set PassWord

        sudo mysql_secure_installation
        mysql -h 127.0.0.1 -P 3306 -u root
        MariaDB [mysql]> set password for root@localhost = password('12');
### Check Status

        sudo systemctl status mysql
### Stop Mysql Service

        sudo /etc/init.d/mysql stop 
### Start mysql without password

        sudo mysqld_safe --skip-grant-tables & 
### Restart

        sudo /etc/init.d/mysql restart
        sudo /etc/init.d/mysql start
### Progress

        ps aux |grep mysql
### Pill Progress

        killall mysqld mysqld_safe
### Sudo

        sudo service mysql status
        sudo service mysql stop
        sudo service mysql start
        sudo start mysql
        sudo stop mysql
        sudo restart mysql
        sudo service mysql restart



### about port(Error: That port is already in use.)

        check: netstat -ntlp
        ready: kill -9 PID
        action: kill -9 pid_number

### Log output is incomplete or unavailable

        journalctl --vacuum-size=1G

# Run Service
## run node or django service
start service

        nohup node server.js & | nohup python manage.py runserver 0.0.0.0:8000 &

## run python service

## run node service
install pm2

        pm2 start server.js

check running service

        pm2 list

# Nginx run Server
## Install Nginx
        sudo apt-get update
        sudo apt-get install nginx
## Nginx Path
        cd /etc/nginx dir

## Set Nginx
        server {
            listen 80;
            server_name www.littlekris.com;
        
            location / {
                proxy_pass http://0.0.0.0:8000;
                proxy_set_header Host $host;
                proxy_set_header X-Real-IP $remote_addr;
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
                proxy_set_header X-Forwarded-Proto $scheme;
            }
        }
        server {
                listen 80;
                server_name meandmrleo.com www.meandmrleo.com;

                location / {
                        proxy_pass http://108.61.222.8:8000/;
                        proxy_set_header Host $host;
                        proxy_set_header X-Real-IP $remote_addr;
                        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
                        proxy_set_header X-Forwarded-Proto $scheme;
                }
        }
        include /etc/nginx/conf.d/*.conf;
        include /etc/nginx/sites-enabled/*;


        sudo systemctl start nginx | sudo service restart nginx | sudo systemctl restart nginx | sudo systemctl status nginx

## Check port 80 used by who
        sudo lsof -i :80
        
## Check fire wall
        sudo ufw allow 80

# Ngrok run PI
install

        https://dashboard.ngrok.com/get-started/setup
start server

         ./ngrok http 8000
