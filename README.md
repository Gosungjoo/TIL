# Json
<br><br>

## Json?
*데이터를 교환 할 때 정해진 규격*

* WEB에서 AJAX 기술에 사용된다
* AJAX 웹 개발 기법

```
{
    "name" : "sanghai"
    "price" : 4,900
    "brand" : "mcdonald"

}
```

*상당히 dict 구조와 유사하다*

[https://jsonlint.com/](https://jsonlint.com/)
*JSON 문법 검사기*


[http://jsonviewer.stack.hu/](http://jsonviewer.stack.hu/)*JSON VIEWER*


---
<br>
<br>

# 파일 교환 Format (*객체,배열* )
## 객체형(object) json
* *객체의 key(이름)은 " "(쌍따옴표)로 묶어야 한다.*






```
{
	"HU": 35,
	"HA": 32,
	"HO": 46,
	"HI": 51
}
```
*다음의 문법을 검사해보자*


*valid json 이면 viewer를 통해 확인해보자*


```
{
	"HU": 35,
	"HA": 32,
	"HO": 46,
	"HI": 51,
    "HI": 55
}
```


*이건 어떨까? 중복 key가 있다*
*중복을 허용하지 않는다.*

---
<br><br>

## 배열형(array) json

```

[1, 2, 3, 4, 5]

```

*이번에는 list형태이다. 프로그래밍 언어에서의 배열과 동일하다. key에 해당하는 값은 index번호를 가르킨다.*


```
[
0:1
1:2
2:3
3:4
4:5
]
```

*이러한 형태로 뷰어에서 보여지게 된다.*

---
<br><br>

## 배열과 객체 자유롭게 다루기
<br><br>
```
{
	"group": "BTS",
	"name": ["aaa", "bbb", "ccc", "ddd"],
	"age": [35, "Unknown,56,55"]

}

```

*객체 내 배열 형태로 저장이 가능하다.*


<br><br>
```
{
    "love" : ["chayoon","jihyo",["computer,notebook,mouse"]]
    "dislike" : ["hungry",777]

}



```

*배열안에 배열도 가능하다*

<br><br>

```
[[1,2,3],[3,4,5],{"A":3,"B":6,"OK":false},true]

```
*배열 안에 객체도 가능하다*

*true/false 자료형도 가능하다*


---
<br><br>

## 실습
```
 {
    "이름": "홍길동",
    "나이": 25,
    "성별": "여",
    "주소": "서울특별시 양천구 목동",
    "특기": ["농구", "도술"],
    "가족관계": {"#": 2, "아버지": "홍판서", "어머니": "춘섬"},
    "회사": "경기 수원시 팔달구 우만동"
 }

```
*출처: [https://ko.wikipedia.org/wiki/JSON/예제](https://ko.wikipedia.org/wiki/JSON#%EC%98%88%EC%A0%9C)*


---
# REST API


## 용어정리
## HTML?
* 웹문서
## HTTP?
* 웹서버와 사용자간의 신호 송신의 순서
## API?
* 컴퓨터의 기능을 실행시키는 방법, 클라이언트가 서버에게 요청할 때 사용하는 명령어


## 클라이언트?
* 정보를 요청하는 곳

## 서버?
* 정보를 제공하는 곳
---
EX
```

운영체제에도 API가 있다.

APP 개발시에 컴퓨터 하드웨어에 직접적으로 접근할 권한이 없다.

앱으로 컴퓨터 또는 모바일의 카메라를 켜고 싶다면?

운영체제에게 부탁(요청)을 한다.

```

```
주식 자동매매 앱을 만든다고 하자.

증권사 서버로 들어가서 주가 정보를 받아야한다.

증권사 서버에 주가 정보 요청
증권사에서 만든 API를 이용해서 요청
증권사에서 요청을 받아준다면 증권사의 정보를 보내준다.

```

```

REST API

HTTP 프로토콜을 사용해서 API를 호출 하는 것


```
