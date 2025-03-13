## dcoker 数据库安装
docker run --name my-postgres -e POSTGRES_USER=root -e POSTGRES_PASSWORD=shuyixiao -e POSTGRES_DB=maxkb -p 5432:5432 -d postgres-with-vector
## 后台服务启动命令 部分依赖需要换源或者翻墙下载 
poetry install
python main.py dev celery
python main.py dev web
python main.py dev local_model
## 未破解省事版安装
docker run -d --name=maxkb --restart=always -p 8080:8080 -v C:/maxkb:/var/lib/postgresql/data -v C:/python-packages:/opt/maxkb/app/sandbox/python-packages registry.fit2cloud.com/maxkb/maxkb
## 注意事项
1、如果本地不包含向量模型，会导致量化失败，这时候需要挂梯子
2、建议使用vscode运行
3、本地python版本为  3.11.9
4、node版本需要18以上
5、如果遇到编码错误则是加密软件导致的，删除所有文件，然后再在git中还原则可以解决
6、数据库需要现在docker中运行

