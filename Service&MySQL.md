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
3) install

        sudo apt-get install nodejs npm
5) check version

        nodejs -v | npm -v
7) install React package

        npm install webpack webpack-cli --save-dev
9) pay attenion

        if some error out when 'npm run build', try run '5)'th first


## Django DB / makemigrations & migrate
- makemigrations & migrate

        python37 manage.py makemigrations | python37 manage.py makemigrations app_name
        python37 manage.py migrate
- pay attention

        if tip 1146, that is smoeone table in db does not exsit, check any *.py
        maybe models.py has been useing, it is earlier run than makemigrations / migrate.
  

## RunServer
runserver

        nohup python3 manage.py runserver 140.82.22.68:8000 &
About fire wall, and relax port

        iptables -I INPUT -p tcp --dport 8000 -j ACCEPT
        

## Install MySQL | mysqlclient | MariaDB
Install 'mysqlclient' on Debian 11 with any error, try install MySQL dependency package first

        sudo apt-get install default-libmysqlclient-dev
Install MariaDB(packages) by what???

        https://runebook.dev/zh/docs/mariadb/installing-mariadb-deb-files/index#installing-mariadb-packages-with-apt
Install mysql-server by apt

        sudo apt install mysql-server
Download & Install Mysql
> downloade
        
        wget https://dev.mysql.com/get/mysql-apt-config_0.8.24-1_all.deb
> install by apt
        
        sudo apt install ./mysql-apt-config_0.8.24-1_all.deb
> remove

        rm mysql-apt-config_0.8.24-1_all.deb
Connect to DB

        mysql -u root -p | sudo mysql | mysql
Create User

        CREATE USER 'root'@'localhost' IDENTIFIED BY 'insert_password';
Authorize

        GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' IDENTIFIED BY 'insert_password' WITH GRANT OPTION;
DOS DB

        Maria[]> show databases；
        Maria[]> create database jal；
        Maria[]> use jal；
        Maria[jal]> 
        Maria[jal]> show tables；
        Maria[jal]> select * from JAL_account;
        Maria[jal]> delete from JAL_asininfo; (Query OK, 170 rows affected (0.008 sec))
        Maria[jal]> drop table JAL_asininfo;
Set PassWord

        sudo mysql_secure_installation
        mysql -h 127.0.0.1 -P 3306 -u root
        MariaDB [mysql]> set password for root@localhost = password('12820839');
Check Status

        sudo systemctl status mysql
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



about port(Error: That port is already in use.)

        check: netstat -ntlp
        ready: kill -9 PID
        action: kill -9 pid_number

Log output is incomplete or unavailable

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

        sudo systemctl start nginx | sudo service restart nginx | sudo systemctl restart nginx | sudo systemctl status nginx

## Check fire wall
        sudo ufw allow 80

# Ngrok run PI
install

        https://dashboard.ngrok.com/get-started/setup
start server

         ./ngrok http 8000
