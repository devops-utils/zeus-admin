```shell
go build -o zeus

cd zeus-admin
go build -o zeus
cd pkg/webui
cnpm install
# yarn install
npm run build:prod
npm run build:work

mysql -h127.0.0.1 -uroot -p
create database zeus default character set utf8mb4 collate utf8mb4_unicode_ci;
use zeus;
create user 'zeus'@'127.0.0.1' identified by 'zeus123456';
grant all privileges on zeus.* to 'zeus'@'127.0.0.1';
create user 'zeus'@'%' identified by 'zeus123456';
grant all privileges on zeus.* to 'zeus'@'%';
flush privileges;

mysql -h127.0.0.1 -uroot -p zeus < scripts/init.sql

sudo docker run -d --name=zeus -p 8072:80 -v "$(pwd)"/data:/data bullteam/zeus-admin:latest
sudo docker run -d --name=zeus -p 8072:80 -v "$(pwd)"/docker/config:/config -v "$(pwd)"/data:/data bullteam/zeus-admin:latest

sudo docker exec -it zeus sh

sudo docker logs -f zeus
sudo docker stop zeus
sudo docker start zeus
sudo docker rm zeus

http://49.232.6.131:8072/#/
admin
123456

sqlite3 data/zeus.db
sqlite3 data/zeus.db ".read scripts/init.sql"

sqlite3 db/boardsprofile.db ".dump" > /var/ftp/profile.sql
sqlite3 test.db ".read /var/ftp/profile.sql"
```

```shell
http://doc.bullteam.cn/guide/install.html

npm install tui-editor
```