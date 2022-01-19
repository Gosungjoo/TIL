# 0119
## 재귀함수

*함수 안에서 자신 혹은 다른 함수를 참고하여 트리를 만드는 형태*


```
def bbq(n):
    if(n < 0):
        return 
    bbq(n-1)
    print(n)



```


```


def bbq(n):
    if(n < 0):
        return 
    print(n)
    bbq(n-1)
    


```
*위 두 결과를 잘 따라가보자*
*코드는 위에서부터 한줄씩 실행되고 함수가 시작되면 다시  함수의 선언부부터 시작이다.*

# 글자 밀기

## 1. a(문자) 를 b(정수)만큼 밀어보자
## 재귀사용
```
#a  아스키
#b  숫자
a,b = input().split()
b = int(b)

def addValue(a,b): #재귀로 풀기
  if(b == 0):
    return a
  else:
    if(a == 'z'):
      return addValue('A',b-1)
    elif(a == 'Z'):
      return addValue('a',b-1)
    else:
      return addValue(chr(ord(a)+1), b-1)

```

*위 코드는 음수일 때 적용이 안된다.*
## 반복문
```
def addValue_2(a,b): #반복문으로 'z'다음문자는 'A' 이런식이면 이렇게
  startAlpha = 'a'
  move = 0
  if('a'<= a <='z'):
    startAlpha = 'a'
    move = ord(a)-ord('a')
  else:
    startAlpha = 'A'
    move = ord(a)- ord('A')


  if ((move+b)//26)%2 == 0:
    print('여긴데')
    return(chr(ord(startAlpha) + (move+b)%26))
  else:
    if(startAlpha == 'A'):
      startAlpha = 'a'
    else:
      startAlpha = 'A'
    return(chr(ord(startAlpha) + (move+b)%26))
```

## 문자열을 밀때는 위 함수를 참조하여 해보자
```
def push_String(a,b): # 람다식도 좋고 map도 좋고 리스트 내장도 써도 되고~ 
  return ''.join([addValue(x,b) for x in a])

push_String('abc', 25)
```


## 10진수 2진수 변환
```
def deci_to_bin(a):
  count = 0
  ans = []
  while(a > 2**count):
    count += 1
  for i in range(count,-1,-1):
    if(a >= 2**i):
      ans.append('1')
      a -= 2**i
    else:
      ans.append('0')


  return ''.join(ans)

print(deci_to_bin(19))

```

## 10진수 2진수 변환(재귀)

```
def recur_deci_to_bin(a):
  if(a == 0):
    return ''
  return recur_deci_to_bin(a//2)+str(a%2)
recur_deci_to_bin(32)
```