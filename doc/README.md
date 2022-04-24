```shell
go build -o zeus

cd zeus-admin
go build -o zeus
cd pkg/webui
cnpm install
# yarn install
npm run build:prod
npm run build:work

sudo docker run -d --name=zeus -p 8072:80 -v "$(pwd)"/data:/data bullteam/zeus-admin:latest

sudo docker exec -it zeus sh

sudo docker logs -f zeus
sudo docker stop zeus
sudo docker start zeus
sudo docker rm zeus

http://49.232.6.131:8072/#/

sqlite3 data/zeus.db
sqlite3 data/zeus.db ".read scripts/init.sql"

sqlite3 db/boardsprofile.db ".dump" > /var/ftp/profile.sql
sqlite3 test.db ".read /var/ftp/profile.sql"  
```

```shell
http://doc.bullteam.cn/guide/install.html

npm install tui-editor
```