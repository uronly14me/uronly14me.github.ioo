---
layout: post
title:  "Javascript에서 Number.isNaN과 isNaN의 차이점"
author: "Sangbeom"
---
```Number.isNaN```이 ```isNaN``` 보다 더 strict하게 검사해준다.

```
Number.isNaN(undefined); // false
Number.isNaN(true); // false
isNaN(false); // false
isNaN(null); // false
Number.isNaN('123'); // false
Number.isNaN(NaN); // true
```
```Number.isNaN```은 ```NaN```이 아닌 값에 대해서는 전부 ```false```이다.

```
isNaN(undefined); // true
isNaN(true); // false. true는 1로 처리되는 듯.
isNaN(false); // false. false는 0으로 처리되는 듯.
isNaN(null); // false. null은 0으로 처리되는 듯.
isNaN('123'); // false. 숫자형 문자열은 Number로 캐스팅이 가능하다.
isNaN(NaN); // true
```
```Number```로 캐스팅이 가능하다면 ```false```이다.

```Number.isNaN```을 더 추천하지만, 개인적으로는 ```Number```로 캐스팅을 많이 하기때문에 ```undefined```를 검출하기에 편한 ```isNaN```을 많이 사용한다.
