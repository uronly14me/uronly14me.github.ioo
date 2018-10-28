---
layout: post
title:  "우분투 unable to locate package 에러"
author: "Sangbeom"
---

ubuntu에서 ```apt install```을 하다가 ```E: Unable to locate package <package>```라는 에러가 났다. 이를 해결하다가 생각보다 찾기 어려워서 남긴다.

## 우분투 리포를 모두 활성화했는지 확인
```
sudo add-apt-repository main
sudo add-apt-repository universe
sudo add-apt-repository restricted
sudo add-apt-repository multiverse
```
## 우분투 업데이트
```
sudo apt update
```

## 패키지 인스톨
```
sudo apt install <package-name>
```
