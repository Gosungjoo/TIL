# 예외처리

<br><br>

## 디버깅
*코드의 상태를 신중하게 출력해가며 심사숙고하는 것보다 효과적인 디버깅 도구는 없다.*

* print() 함수 활용
* IDE의 디버깅 모드 활용


<br><br>

## 코드를 작성하다가
* 에러메세지가 발생하는 경우
  * 해당 위치를 찾아 메세지를 해결 -> 감사하자

  <br><br>
* 로직 에러가 발생하는 경우
  * 명시적인 에러 메세지 없이 예상과 다른 결과가 나온 경우..
    * 정상적으로 동작한 코드 이후 작성된 코드를 생각
    * 전체 코드를 살펴봄
    * 휴식을 가져봄
    * 누군가에게 설명해봄..
    * ....

<br><br>

# 에러 / 예외

## 문법 에러(Syntax Error)
* 프로그램이 실행 할 수 없다.
* 문제가 발생했을 때 ^(caret)기호로 표시


## 예외(Exceptions)의 종류
* **TypeError**
  * 타입이 불일치 하는 경우
  * argument 누락 된 경우

* **ValueError**
  * 타입은 올바르나 값이 올바르지 않는 경우
* **indexError**
  * 인덱스가 존재하지 않거나 범위를 넘어서는 경우
* ZeroDivisionError
  * 0으로 나누고자 할때
* NameError
  * name space 상에 존재하지 않을 때

* KeyError
  * 해당키가 존재하지 않는 경우
* Module Error
* import Error
  * Module은 있으나 세부 항목이 없는 경우
* indentation Error
  * 텝, 스페이스바 사용 오류
<br><br><br>

# 예외처리

## try / except / else / finally

## try:
* 예외가 발생할 것 같은 구간을 넣는다.

## except as 변수:
* 예외가 발생하면 나오는 구간을 넣는다.

## else:
* 예외가 발생하지 않으면 나온다.

## finally:
* 위의 코드가 끝난 후 무조건 진행된다.


```
try:
  a = int(input()) #오류가 발생 가능한 부분
except:
  print('숫자를 입력하세요')
else:
  print('좋습니다',a)


```

## raise
* 강제로 예외 발생

## assert
* 조건부 예외 발생
  * 조건이 거짓일 경우 예외를 발생시킨다.
  