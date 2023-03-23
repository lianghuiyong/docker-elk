[![Security Status](https://s.murphysec.com/badge/lianghuiyong/docker-elk.svg)](https://www.murphysec.com/p/lianghuiyong/docker-elk)

<h1 align="center">ELK 8.0.1 on <b>Docker</b></h1>
<h2 align="center">Elastic 部署工具</h2>

<p align="center">
   <a>
      <img src="https://img.shields.io/badge/ElasticSearch-8.0.1-blue?style=flat&logo=ElasticSearch" alt="Elastic Stack Version 7^^">
   </a>
   <a>
      <img src="https://img.shields.io/badge/Kibana-8.0.1-blue?style=flat&logo=Kibana" alt="Elastic Stack Version 7^^">
   </a>
   <a>
      <img src="https://img.shields.io/badge/Logstash-8.0.1-blue?style=flat&logo=Logstash" alt="Elastic Stack Version 7^^">
   </a>
   <a>
      <img src="https://img.shields.io/badge/FileBeat-8.0.1-blue?style=flat&logo=ElasticSearch" alt="Elastic Stack Version 7^^">
   </a>
   <a href="./LICENSE">
      <img src="https://img.shields.io/badge/license-MIT-blue.svg">
   </a>
</p>

# 使用
## 1、初始化 Certs
```shell
docker-compose -f docker-compose.certs.yml run --rm certs
```
## 2、初始化 Keystore
```shell
docker-compose -f docker-compose.keystore.yml run --rm keystore
```
## 3、配置Kibana
```
将生成的.env.kibana.token内『KIBANA_SERVICE_ACCOUNT_TOKEN=』后的token， 
复制到kibana/config/kibana.yml的『elasticsearch.serviceAccountToken』
```

## 4、启动ELK
```shell
docker-compose -f ./docker-compose.yml up  --build --remove-orphans
```
## 5、页面账号登录
[ElasticSearch：https://localhost:9200](https://localhost:9200/)
- 账号：(env文件下的ELASTIC_USERNAME字段)
- 密码：(env文件下的ELASTIC_PASSWORD字段)

[Kibana：http://localhost:5601](http://localhost:5601/)
- 账号：(env文件下的ELASTIC_USERNAME字段)
- 密码：(env文件下的ELASTIC_PASSWORD字段)
