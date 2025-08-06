
```
# 删除所有容器（包括运行中和已停止的)
docker rm -f $(docker ps -aq)

# 删除所有镜像
docker rmi -f $(docker images -q)

# 在Windows PowerShell中如果遇到语法问题，可以改用：
docker ps -aq | ForEach-Object { docker rm -f $_ }
docker images -q | ForEach-Object { docker rmi -f $_ }

# 如果只需要删除当前项目的资源，更安全的方式是使用过滤条件：
# 删除特定名称的容器

docker ps -a --filter "name=ruoyi" -q | ForEach-Object { docker rm -f $_ }
# 删除特定标签的镜像

docker images --filter "label=com.docker.compose.project=ruoyi" -q | ForEach-Object { docker rmi -f $_ }