
# seletion sort
```
[1,5,3,2,11,9]

앞에서부터 시작한다. index 0을 시작으로 그 뒤부터 비교하여 제일 작은 것으로 교체한다.

ex) 
[1,5,3,2,11,9] index : 0
[1,3,5,2,11,9] index : 1
 -> index : 1의 처음 값은  5였으나
 3이 그 다음 작으므로 위치를 바꾼다.
[1,2,5,3,11,9] index : 1
 -> 3이였으나 다음을 확인했는데
  2가 더 작으므로 위치를 바꾼다.

  ....

[1,2,3,5,9,11] 

```
## CODE
```
arr = [1,5,3,2,11,9]
index = 0


while(index < len(arr)):
    temp = index+1
    arr[index]
    for i in range(temp,len(arr)):
        if arr[index] > arr[i]:
            arr[index] , arr[i] = arr[i],arr[index]
    index+= 1
print(arr)
```
# bubble sort
* 앞에서부터 2개씩 순차적으로 비교하여 앞뒤로 정렬한다.
* 첫 줄을 다 돌리면 맨 끝에 가장 큰 값이 온다.
* 끝에 정렬 된 경우 지역적으로 가장 큰 값이다. 즉 다음 줄에서는 포함하지 않는 것이 속도향상에 도움이 된다.
* n번 실행하면 전부 정렬된다.

```
arr = [1,5,3,2,11,9]

for i in range(len(arr)-1,0,-1):
  for j in range(0,i):
    if(arr[j] > arr[j+1]):
      arr[j],arr[j+1] = arr[j+1],arr[j]

print(arr)
```
# binary search
* 가장 기초 탐색법
* 정렬된 데이터를 통해서 구할 수 있음
```
N = int(input())
arr = list(map(int,input().split()))
key = int(input())

arr.sort()

def bs(s,e,key):
    if(s > e):
        return False
    if(arr[(s+e)//2] == key):
        return True
    elif(arr[(s+e)//2] > key):
        return bs(s,(s+e)//2 -1,key)
    elif(arr[(s+e)//2] < key):
        return bs((s+e)//2+1,e,key)

print(bs(0,N-1,key))
```


# Parametric algo


