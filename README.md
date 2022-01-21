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


<br><br><br> 

# 인코딩과 디코딩

## python 기준 인코딩
* 객체를 Json 데이터로 만드는 과정(*dump*)

## python 기준 디코딩
* Json 데이터를 객체로 만드는 과정(*load*)

<br><br>

# encoding

```
import json

a = dict()
a['name'] = 'shanghai'
a['price'] = 4900


#덤프를 한다면?
# indent? 들여쓰기
b = json.dumps(a,indent=4)
print(b)

```
```
$ python test3.py


{
    "name": "shanghai",
    "price": 4900
}

```
* *json.dumps* 함수를 이용하여 인코딩 하는 코드

<br><br>



<br><br>
# decoding

```
import json

a = dict()
a['name'] = 'shanghai'
a['price'] = 4900



# indent? 들여쓰기
b = json.dumps(a,indent=4)
#로드를 한다면?
c = json.loads(b)

print(c)

```


```
$ python test3.py
<class 'dict'>
{'name': 'shanghai', 'price': 4900}
```
* *json.loads* 함수를 사용하여 json 데이터를 객체로 받는다.


# 형변환
```
python의 dict
= json의 객체

python의 list
= json의 array

python의 int
= json의 int

...


```

# 주의 사항

* 아래 코드는 오류가 난다.

```
a = json.load(str)

```

```
a = json.loads(str)

```
* 함수에는 s가 붙는다.

 *dumps* , *loads* (O) 
 
 *load* , *dump*  (X)
<br><br><br><br>

 ---
 # 파일 읽기/쓰기
 * python 에서 json 파일을 위해서 file open을 해야한다.

 ```
    #파일 읽기

f1 = open('파일이름 스트링형태.확장자','r',encoding = 'utf-8') 

str1 = f1.read()

    


    #파일 쓰기
f2 = open('파일이름 스트링형태.확장자','w',encoding = 'utf-8') 

f2.write('이 내용을 저장했습니다')
 
 


    # 꼭 open 했으면 닫아야한다.

 f2.close
 f1.close

 ```


 <br><br><br><br>


 # 실습
 ```
 import json


f1 = open('test2.json','r',encoding = 'utf-8') # 파일 읽기
f2 = open('bbq.json','w',encoding = 'utf-8') # 파일 읽기

str_f1 = f1.read()
txt = json.loads(str_f1)
save_txt = json.dumps(txt,indent = 4)
f2.write(save_txt)


f2.close()
f1.close()

``` 
## 파일읽기
* f1은 파일을 읽는다.(r 읽기 모드) f1은 파일의 위치(ptr , 포인터가 들어가 있다.)
* f2는 저장할 파일을 만든다. (w 쓰기모드)
---
## 파일 json 처리하기
* str_f1은 f1의 파일을 str형식으로 만들어준다.
* json.loads 함수는 str을 형식에 맞추어 python dict 형태로 만들어준다.
* json.dumps 함수는 python 객체를 json 형태의  객체로 만들어준다.
---
## 파일 저장하고 ptr(포인터) 닫기
* f2는 그 객체를 만든파일에 save_txt의 내용을 저장한다.
* f2포인터를 닫는다.
* f1포인터를 닫는다.


# Web 에서 가져오기

```
import requests
import json


# requests 를  이용해서 서버에 page 요청

ret=requests.get('http://api.tvmaze.com/singlesearch/shows?q=narcos&embed=episodes')





# a 변수 하나 만들어서 그 변수에 text 방식으로 저장

a = json.loads(ret.text) #디코딩 ret에 .text를 붙이는 것




a= a['_embedded']['episodes'][3]['image']['original']
print(a)

# 해당 링크에 뭐가 있는지 알아보자.

```


```
https://static.tvmaze.com/uploads/images/original_untouched/16/41475.jpg
```
