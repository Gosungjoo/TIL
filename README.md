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