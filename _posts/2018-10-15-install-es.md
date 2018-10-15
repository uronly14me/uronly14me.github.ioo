---
layout: post
title: "Ubuntu에 Elasticsearch 6.x 설치"
author: "Sangbeom"
---

## Elasticsearch 설치하기
```
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://artifacts.elastic.co/packages/6.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-6.x.list
sudo apt-get update && sudo apt-get install elasticsearch
```

## elasticsearch.yml 수정하기
```
sudo vi /etc/elasticsearch/elasticsearch.yml
...
network.host 0.0.0.0
```
i를 눌러 insert mode에서 파일을 수정하고 esc를 눌러 normal mode로 나온다음 ₩:wq₩로 저장을 한다.

## Elasticsearch 서비스로 실행
```
sudo /bin/systemctl daemon-reload
sudo /bin/systemctl enable elasticsearch.service
sudo /bin/systemctl start elasticsearch.service
```

## Elasticsearch 서비스 확인
```
curl 127.0.0.1:9200
```
