<!-- dcoker 数据库安装 -->
docker run --name my-postgres -e POSTGRES_USER=root -e POSTGRES_PASSWORD=shuyixiao -e POSTGRES_DB=maxkb -p 5432:5432 -d postgres-with-vector
## 后台服务启动命令
python main.py dev celery
python main.py dev web
python main.py dev local_model

## 注意事项
1、如果本地不包含向量模型，会导致量化失败，这时候需要挂梯子
2、建议使用vscode运行
3、本地python版本为  3.11.9
4、node版本需要18以上