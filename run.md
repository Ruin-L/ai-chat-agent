## dcoker 数据库安装
docker run --name my-postgres -e POSTGRES_USER=root -e POSTGRES_PASSWORD=shuyixiao -e POSTGRES_DB=maxkb -p 5432:5432 -d postgres-with-vector

## vscode插件安装 插件自带虚拟环境安装后可以在vscode控制台启动服务，如果不安装则会提示No module named 'Crypto'等报错
![alt text](image-1.png)
## 后台服务启动命令 部分依赖需要换源或者翻墙下载 
<!-- 可以换源 -->
poetry source add --priority=primary mirrors  https://mirrors.aliyun.com/pypi/simple/
<!-- 创建虚拟环境 -->
python -m venv .venv
<!-- 进入虚拟环境 -->
终端进入 cd .venv\Scripts
启动虚拟环境 activate.bat

poetry install
## 三行命令启动
python main.py dev celery
python main.py dev web
python main.py dev local_model

## 未破解省事版安装
docker run -d --name=maxkb --restart=always -p 8088:8080 -v C:/maxkb:/var/lib/postgresql/data -v C:/python-packages:/opt/maxkb/app/sandbox/python-packages registry.fit2cloud.com/maxkb/maxkb
## 注意事项
1、如果本地不包含向量模型，会导致量化失败，这时候需要挂梯子
2、建议使用vscode运行配合上述截图的插件
3、本地python版本为  3.11.9
4、node版本需要18以上
5、如果遇到编码错误则是加密软件导致的，删除所有文件，然后再在git中还原则可以解决
6、数据库需要先在docker中运行
7、退出虚拟环境deactivate.bat

