# 알고리즘 정리




# 탐색방법 (완전 탐색 / 이진탐색)

* 처음 인덱스부터 크기를 비교한다. 맨 마지막에 결과가 나오는 경우
자료의 길이가 N일 때 N번 연산하므로 O(N)이다.

*처음부터 코드를 돌린다.*


```
# 존재하는지 여부를 반환하는 함수

def isin():
    list_temp = [1,2,3,4,5,6,7,8,9]
    search_key = 4
    for i in list_temp:
        if search_key == i:
            return True


```
        
```
# 찾은 리스트의 위치를 반환하고 싶다면?
def wherein():
    list_temp = [1,2,3,4,5,6,7,8,9]
    search_key = 4
    for i in range(len(list_temp)):
        if search_key == list_temp[i]:
            return i
```

*다차원도 가능하다.*



```
# 다차원 리스트의 위치 반환
def wherein():
    list_temp = [[1,2,3],[4,5,6],[7,8,9]]
    search_key = 4
    for i in range(len(list_temp)):
       #앞의 인덱스를 결정한다.
        for j in range(len(list_temp[i])):
         # 나머지 뒤의 인덱스를 결정한다.
            if search_key == list_temp[i][j]:
             # 위에 결정된 두 인덱스를 통해서 list에 접근하여 비교한다.
                return i,j
```

<br><br><br><br>
---

## 탐색 방법 (정렬된 데이터)
* *List*의 정 중앙의 데이터와 비교한다. 같으면 그 위치를 반환하면 되고 크거나 작으면 중앙를 기준점으로 *List*를 나누어 절반의 구간에서 다시 비교한다.

* 제일 유용한 이진탐색의 소모시간은 O(log N)이다. 왜냐하면 1번 계산할 때 절반이 사라지므로 k번 계산한다면 2^k = N 이며 log N = k 로 유도 할 수 있다.


<br><br><br><br>
* 이진 탐색 재귀함수
```
def search(search_key = 3,list_sorted = [1,2,3,4,5,6,7,8]):

        c = int(len(list_sorted)/2) # c는 리스트 중앙의 index
        if search_key == list_sorted[c]:
            return c
        elif search_key > list_sorted[c]:
            return search(search_key,list_sorted[c+1:])
        else:
            return search(search_key,list_sorted[:c])

    
```
<br><br><br><br>
*while 문도 동일하게 작성할 수 있다.*

* 이진 탐색 반복문
```
def search(search_key = 3,list_sorted = [1,2,3,4,5,6,7,8]):
    
    while(True):
        c = int(len(list_sorted)/2) # c는 리스트 중앙의 index
        if search_key == list_sorted[c]:
            return c
        elif search_key > list_sorted[c]:
            list_sorted = list_sorted[c+1:]
        else:
            list_sorted = list_sorted[:c])


```
*위 코드는 전부 list안에 있다고 가정을 한 상태이다. 없는 조건을 확인하려면 search_key in list_sorted 등을 통해서 확인해도 되고 마지막 조건에 list의 길이가 1일 key와 같지 않을 경우 return 값을 -1 해도 된다.*

<br><br><br><br>

# 정렬 방법

*위에서 유용하게 쓰는 이진정렬 방법은 정렬된 데이터에 한해 가능하다.
데이터를 어떻게 정렬하는지 알아보자*


## 순차정렬
* 순서대로 차례차례 비교하면서 정렬하는 방법
* 시간 복잡도는 O(N^2)이다. 왜냐하면 list의 for문을 N번 진행하는데 각각의 길이는 1,2....N이다. 1,2, ... N을 전부 더하면  총 N*(1+N)*(1/2) 번의 반복문을 수행한다. Big - O계산법에 의하여 (N^2)가 된다.
```
def MySort(list_temp = [1,5,2,3,4,9,6]):
    for j in range(len(list_temp)-1):
        for i in range(len(list_temp)-j-1):
          if list_temp[i] >list_temp[i+1]: # 정렬이 안된 경우
            temp = list_temp[i]
            list_temp[i] = list_temp[i+1]
            list_temp[i+1] = temp # 값을 바꿔준다.
    return list_temp
    #이렇게 for 문을 1회 돌면 맨 끝에 값은 제일 큰 값이다.
    #list의 길이만큼 반복하면 제일 큰 값부터 차곡차곡 쌓인다. 

```
<br><br>

## Quik 정렬


* 리스트 중간 값을 기준으로 왼쪽으로 작은 값 오른쪽으로 큰 값을 둔다.
* 새로 만들어진 리스트에도 계속 수행해준다.
* 즉 1,5,2,4,3 이면 정 가운데에 있는 값은 2이다.
* 2보다 작은 리스트 [1] 기준[2] [5 ,4 ,3]  이렇게 만들어준다.
* 1는 더이상 할 필요가 없다. [5 ,4 ,3] 에서 다시 가운데 값을 기준으로 나눈다.
* [3] 기준[4] [5] 이렇게 나뉘고 종료된다.

```
# 재귀함수로 구현한 Quik정렬

def MyQuik(list_temp = [1,5,2,3,4,9,6]):

    if(len(list_temp) == 1):
      return list_temp
    if(len(list_temp) == 0):
      return []
    # 재귀함수의 종료 조건이다. 리스트가 1개 남아있으면 더이상 비교 할 수가 없기 때문이다.

    
    pivot = list_temp[int(len(list_temp)/2)]
    # 중앙에 있는 값을 가져온다.


    lList = []
    pivot_list = [pivot]
    rList = []
    # 추후에 합치기 위해서 만들어준다.


    for i in list_temp:
      if(i < pivot):
        lList.append(i)
      elif(i > pivot):
        rList.append(i)
    # 기준 값보다 작으면 l List에 넣고 아니면 r List에 넣는다.



    return MyQuik(lList)  +pivot_list + MyQuik(rList)
    # 작은 것과 큰 것을 순서에 맞추어서 합치고 return 한다.

```

```

def MyQuik(list_temp = [1,5,2,3,4,9,6]):

    if(len(list_temp) == 1):
      return list_temp
    if(len(list_temp) == 0):
      return []

    
    pivot = list_temp[int(len(list_temp)/2)]
    lList = []
    pivot_list = [pivot]
    rList = []

    for i in list_temp:
      if(i < pivot):
        lList.append(i)
      elif(i > pivot):
        rList.append(i)


    return MyQuik(lList) + pivot_list + MyQuik(rList)


```