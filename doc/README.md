```shell
go build -o zeus

cd zeus-admin
go build -o zeus
cd pkg/webui
cnpm install
# yarn install
npm run build:prod
npm run build:work

sudo docker run -d --name=zeus -p 8072:80 -v $pwd/data:/data bullteam/zeus-admin:latest
sudo docker logs -f zeus
sudo docker stop zeus
sudo docker start zeus
sudo docker rm zeus

http://49.232.6.131:8072/#/
```

```shell
http://doc.bullteam.cn/guide/install.html

npm install tui-editor
```