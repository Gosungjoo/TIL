# Stack
## 스택이란?
* 물건을 쌓아 올리듯 자료를 쌓아 올린 형태의 자료구조

## 스택은 선형 구조
* 선형구조
  * 자료 간의 관계 1 - 1 ex) 스택, 큐
* 비선형구조
  * 자료 간의 관계 1 - N ex) 트리

## Stack의 설명
* 마지막에 삽입한 자료를 가장 먼저 꺼냄
* 후입선출(LIFO : last in first out) 이라고 부른다.
* 스택의 마지막 원소의 위치를 top
* push, pop, isempty, peek

## 스택 구현 고려사항
* 리스트를 통한 구현
  * 구현이 용이하지만 리스트의 크기를 변경하는 것은 큰 overhead 발생
* 배열처럼 사이즈 고정
  * 사이즈를 바꿀 수가 없다.
* 동적 연결리스트 사용
  * 구현이 힘들고 고정사이즈에 비해서 연산량이 상당히 많다.


# 메모이제이션(Memoization)

## 정의
* 컴퓨터 프로그램을 실행할 때 이전에 계산한 값을 메모리에 저장하여 매번 다시 계산하지 않도록하는 기술

* DP의 핵심이 되는 기술
<br><br><br><br>
# 동적 계획법
* 모든 연산의 구조를 구성한 다음 하위 연산이 상위 연산을 포함한다면 미리 하위 연산을 처리 한 후에 상위 연산에 포함 시키는 것.



<br><br><br><br>

# 수업내용 (0125)


## 리스트의 set을 활용한 연산
* list를 set으로 변경하면 중복을 제거 할 수 있다.
```
list1 = ['A','B','A']

list1 = set(list1)
list1 = list(list1)



```



```
list1 = ['A','B','C','D']
list2 = ['B','C','E','F']

# 리스트의 합집합
union = list(set(list1)|set(list2))

# 리스트의 교집합
inter = list(set(list1)&set(list2))

# 리스트의 차집합
comple = list(set(list1)-set(list2))

# 리스트의 합집합 - 교집합
uni_inter = list(set(list1)^set(list2))

```