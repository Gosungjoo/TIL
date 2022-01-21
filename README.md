# 파이썬을 이용한 데이터 수집

## JSON 데이터를 원하는 결과물로 변환

## 파일 입력 방법
 *open(file, mode = 'r', encoding =None)*
 * file : 파일명
 * mode : Text 모드
 * encoding : 인코딩 방식 *utf-8이 기본*

 ```
 f = open('myText', 'w')


 ```


```
with open('mytxt') as f:
    read_data = f.read()


#with 키워드가 없으면 닫아줘야함
f.closed
```


## Json 데이터 읽기

* dict.get(key,default)
* dict[key]

*두개는 무슨 차이가 있을까?*

### get *vs* []
* []는 key가 없으면 error 발생
* get은 기본 값을 보낸다.

### 예외처리의 경우
* []를 쓴다.

### 일반적인 상황
* get
