# 投资管理系统

投资管理系统的原型系统，采用微服务架构构建。

## 编译方法

在项目根目录下，执行以下命令：

```shell
./start-infrastructure.sh         #启动基础设施
./createdb.sh                     #创建数据库 (注：需要mysql或mariadb命令行支持)
./migratedb.sh                    #初始化数据库
./build-application.sh            #编译应用程序
```

## 使用方法

在根目录下启动：

```shell
./start-infrastructure.sh         #启动基础设施
./createdb.sh                     #创建数据库  (注：需要mysql或mariadb命令行支持)
./migratedb.sh                    #初始化数据库
./start-application.sh            #启动应用程序
```

访问以下地址，通过HAL-Browser查看数据模型，进行增删改查。

```shell
http://localhost:8080/api
```

停止：

```shell
./stop-application.sh             #关闭应用程序
./stop-infrastructure.sh          #关闭基础设施
```

## 已集成组件

mariaDB

kafka/kafka streams

docker/docker-compose

REST with HAL and HAL browser

actuator

zuul(api gateway)

slf4j on logback with logstash's JSON encoder

i18n support

service discovery with Eureka

## 服务API

```lua
/funds GET/POST/DELETE
/funds/{fundId} GET/PUT/DELETE
/funds/{fundId}/fund-accounts GET/POST/DELETE
/funds/{fundId}/external-capital-accounts GET/POST/DELETE

/fund-accounts GET
/fund-accounts/{fundAccountId} GET/PUT/DELETE
/fund-accounts/{fundAccountId}/portfolios GET/POST/DELETE

/portfolios GET
/portfolios/{portfolioId} GET/PUT/DELETE

/external-capital-accounts GET
/external-capital-accounts/{externalCapitalAccountId} GET/PUT/DELETE
/external-capital-accounts/{externalCapitalAccountId}/external-trade-accounts GET/POST/DELETE
/external-capital-accounts/{externalCapitalAccountId}/eca-cash-pools GET/POST/DELETE

/external-trade-accounts GET
/external-trade-accounts/{externalTradeAccountId} GET/PUT/DELETE

/eca-cash-pools GET
/eca-cash-pools/{ecaCashPoolId} GET/PUT/DELETE
```
