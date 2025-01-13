# 1.mac安装

用 homebrew 安装：

```bash
brew install kafka
```

配置文件路径：/opt/homebrew/etc/kafka/server.properties

```bash
# 配置监听端口
# 以下为默认配置，是注释掉的，将注释去掉
#listeners=PLAINTEXT://:9092
listeners=PLAINTEXT://:9092
# 还可指定IP
listeners=PLAINTEXT://xx.xx.xx.xx:9092
```

启动 zookeeper：

```bash
brew services start zookeeper
```

启动 kafka：

```bash
brew services start kafka
```

检查是否正确启动：

```bash
lsof -i :9092
```

