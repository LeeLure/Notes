### 1.拉取官方镜像并创建容器
```
docker run -d \
  --name ruoyi-mysql \ # 容器名
  --network host \ # 网络
  -e MYSQL_ROOT_PASSWORD=123456 \ # 初始密码
  -e MYSQL_DATABASE=ry-vue \ # 数据库名
  -p 33306:3306 \ 端口映射
  -v /docker/mysql/data:/var/lib/mysql \ #挂载
  mysql:8.0 \
  --default-authentication-plugin=mysql_native_password \ # 将mysql8.0默认密码策略 修改为 原先 策略 (mysql8.0对其默认策略做了更改 会导致密码无法匹配)
  --character-set-server=utf8mb4 \
  --collation-server=utf8mb4_general_ci
```

### 2.导入 .sql 文件
##### 1.进入容器 
```
# 进入MySQL命令行 -u后直接跟用户名 
docker exec -it ruoyi-mysql mysql -uroot -p123456
```
##### 2.创建数据库
```
# 执行SQL命令创建数据库（假设数据库名为ry-vue-plus，符号！）
CREATE DATABASE `ry-vue-plus`;

exit
```
##### 3.导入
###### 1.容器内部导入
```
# 选择要导入的数据库
USE ry-vue;

# 路径
source /tmp/ry-vue-plus.sql;

# 验证
SHOW TABLES;
```
###### 2.docker 直接导入 
```
# 1. 复制文件到容器
docker cp /docker/sql/ ruoyi-mysql:/tmp/

# 2. 执行导入
docker exec -i ruoyi-mysql mysql -uroot -p123456 ry-vue < /tmp/ry-vue-plus.sql
```
